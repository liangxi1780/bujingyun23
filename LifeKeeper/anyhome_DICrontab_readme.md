# DICrontab
This is a php class implement a timetable service using format string like linux crontab, dependence on swoole-extension.

Thanks to the project [swoole-crontab](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468d524eaec20c31a5c8934491672f55bc62ad2f0bff5bf4759517720d751014fa), I learned how to analyze the crontab string.

DICrontab is not the same as [swoole-crontab](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468d524eaec20c31a5c8934491672f55bc62ad2f0bff5bf4759517720d751014fa), that's a complete application, and DICrontab is just like a tool, a simple library, a class, you can inclued it and use is in your project.

# Quick start
```
 When('0 */20 * * *')
	->Then(function ($userParams)
	{
		echo 'crontab called';
		return false;//return false if you want to cancle this cron.
        }, $userParams
        );
//The callback function will be called every 20 minitues.
```
If you just want to test when will the ticker tick next time
Use the Next() function instead, Next() will return the Iterator of the time table.
Also you can use From(startTime) to asume the cron start at what time you need instead of time().
```
$iterator = $crontab->When('* */20 * * *')
		//->From( mktime(14, 00, 00, 3, 3, 2016) )//Optional
		->Next();

$count = 0;//only print next 10 cron.
foreach($nextTickTime in $iterator)
{
	if($count++  worker_id==0)" to add only one ticker.

# Description
While working my on swoole-framework [DIServer-framwork](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046387b9f1f3ddda29408dd5220c8e6898fe4a1fc3cae6b409bca5c4dd14e830e52), I find is not easy to implement some timer job like send a message to every clients on every Monday to Friday, swoole_tick provides a high accuracy tick service, but only can tick every same micro-seconds or tick atfer some micro-seconds from now.

What I need is something like crontab in Linux, using a format string can easily like "0 0 \* \* mon-fri", and the callback function will called while time's up.

At first I just want to use it as a plugins in [DIServer-framwork](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046387b9f1f3ddda29408dd5220c8e6898fe4a1fc3cae6b409bca5c4dd14e830e52), but after I finished it I find out it's a independent job, so I create this project.

# Difference
As the high accuracy provieded from swoole-extension, not like Linux-crontab, we can set up HIGH LEVEL cron like "\*/20 0 0 \* \* fri", while using 6 params, the format will be "second minute hour day month week"; As 5 params is "minute hour day month week", and it will called on second 1 in that minute like linux-crontab.

# Example
Here is some example I used to test the Ticker, if you find any bugs, please [notes](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a3639bde6f83adb7e220a8d46344263bcdadaa8aba776f740bcae9458387473f) me.
```
private $cronString = [
		'* */1 * 3 3 *'          => 'every seconds in Mar 3th.',
		'30 30 21 * * *'         => '21:30:30 on every day.',
		'15,30,45,0 * 23 * * 6'  => 'every 0,15,30,45 seconds in 23 every Saturday.',
		'0 0 */1 * * *'          => 'every hour at 0 minute and 0 seconds.',
		'0 0 4 1 jan *'          => 'every 4:00:00 at January 1st.',
		'* * 7 * * *'            => 'every seconds in 7 o'clock every day.',
		'0-59/2 20 0-23/2 * * *' => 'every 2 seconds in every 20 minutes at every 2 hours in a day.',
		'0 6-12/3 * 2 *'         => 'In February, every 3 hours in 6 o'clock to 12 o'clock.',
		'0 17 * * 1-5'           => 'every 17:00:01 on Monday to Friday.',
		'0 11 4 * mon-wed'       => 'Every 11:00:01 on 4th of a month or in Monday to Wednesday',
		'10 1 * * 6,0'           => 'every 1:10:01 on Saturday and Sunday',
		'45 4 1,10,22 * *'       => '4:45:01 on every 1st,10th,22th in a month.',
		'0,30 18-23 * * *'       => 'every 0,30 minutes in 18-23. Tips:23:30 will called.',
		'*/1 * * * * *'          => 'every seconds',
		'* * * * * *'            => 'every seconds',
		'0 23-7/1 * * *'         => 'equals to "0 23,0-7 * * *"',
	];
```

# Shorthand
While using Month or Week, you can use 'fri' instead of '5' means the friday, the shorthand support was listed below:
```
//Case is ignored
const SHORT_MAP = [
		'sun'       => 0,
		'sunday'    => 0,
		'mon'       => 1,
		'monday'    => 1,
		'tues'      => 2,
		'tue'       => 2,
		'tuesday'   => 2,
		'wed'       => 3,
		'wednesday' => 3,
		'thur'      => 4,
		'thu'       => 4,
		'thursday'  => 4,
		'fri'       => 5,
		'friday'    => 5,
		'sat'       => 6,
		'saturday'  => 6,
		'jan'       => 1,
		'january'   => 1,
		'feb'       => 2,
		'february'  => 2,
		'mar'       => 3,
		'march'     => 4,
		'apr'       => 4,
		'april'     => 4,
		'may'       => 5,
		'jun'       => 6,
		'june'      => 6,
		'jul'       => 7,
		'july'      => 7,
		'aug'       => 8,
		'august'    => 8,
		'sep'       => 9,
		'sept'      => 9,
		'september' => 9,
		'oct'       => 10,
		'october'   => 10,
		'nov'       => 11,
		'november'  => 11,
		'dec'       => 12,
		'december'  => 12
	];
```





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1fbb91eb7fb17c54abdd5c5201666b6fe08f324f3497b4c9871ed2a333163514bb8bdc1d756b8bd9fd789e119656aefa)
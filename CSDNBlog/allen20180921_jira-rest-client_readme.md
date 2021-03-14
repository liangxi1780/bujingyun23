# Jira API client for Laravel 5.5+

Perform various operations of [Jira APIs](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484e81534d5377c5bcd0d90d81c50d6ddebfd4eb1d0c0e846136300d03c1928b705d64e7f95ab0edede71ed36703648b007) with Laravel 5.5+

The aim of the package is to make it easier to communicate with the API. By default the response from the request is not altered in any way.
By creating your own implementation or de simple helpers provided with the package you are able to integrate Jira the way you like.

## Installation

To get the latest version of `jira-rest-client`, run the following command
```shell
composer require kenuo/jira-rest-client
```
Do note that not all methods have been implemented yet.

Laravel 5.5 uses Package Auto-Discovery, so doesn't require you to manually add the ServiceProvider.

## Laravel 5.5:

If you don't use auto-discovery, add the ServiceProvider to the providers array in `config/app.php`
```php
'providers' => [
    // ...

    Atlassian\JiraRest\JiraRestServiceProvider::class,
],
```

Also locate the `Aliases` key in your `config/app.php` file and register the Facade:

```php
'aliases' => [
    // ...

    'Jira' => Atlassian\JiraRest\Facades\Jira::class,
],
```
Copy the package config to your local config with the publish command:
```shell
php artisan vendor:publish --provider="Atlassian\JiraRest\JiraRestServiceProvider"
```

Update the .env with your proper credentials using JIRA variables from `config/atlassian/jira.php`.

## Usage

The core of this package is a direct reflection of the Jira API mean that all request classes don't format the response you get from the API.
This desicion was made so the package is more versitile allowing users to handle the response of the requests to their own wishes. 

For example, to fetch a specific issue you could do the following
```php
$request = new \Atlassian\JiraRest\Requests\Issue\IssueRequest;
$response = $request->get('ISSUE-3');
```

All responses are an instance of `\GuzzleHttp\Psr7\Response` [Read more](http://u.720life.cn/g/0784fbd8cf7d11bb05f8e55c14eb436b1caa027b18f8657461be6ab851f7a8aac6675cabfb9736ec874179a14d0673d5) so in order to get the json response you could do the following:
```php
$response = json_decode($response->getBody(), true);
``` 
Which will return a response like seen in the [API](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484e81534d5377c5bcd0d90d81c50d6ddebfd4eb1d0c0e846136300d03c1928b705db93b5bbf9ce0b85ae59aaabec0f63fd1e1636add65e4e4060f0996dbeba4a72d2fc15fa620483e151e9ed2a26dd04c6)

### Helpers
Now because for the most part you don't want to spend time writing the requests yourself there are some useful helpers to get you communicating with the api.

To fetch a single issue you can use the following code:
```php
$issue = jira()->issue('ISSUE-3')->get();
```

Or use the facade if you prefer:
```php
$issue = \Jira::issue('ISSUE-3')->get();
```

### Middleware
To alter the Guzzle Client used for requests you can add middleware to alter the options. To add new middleware you need to alter `config/atlassian/jira.php` and add the class to the `client_options` array.
```php
'client_options' => [
    'auth' => \Atlassian\JiraRest\Requests\Middleware\BasicAuthMiddleware::class,
],
```
By default the `BasicAuthMiddleware` is added and used for authentication with Jira. (Sessions and OAuth tokens are WIP)

ps. I'm not quite happy with the middleware as it is implemented at this time but I do want to incorporate them in a way.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee708ba52e9e10d3e1e27d962607b7c4430ca61d0e54af9a4daaad6bff8b2b9e07104b6991b025c0dd65d4f55c5801a4919e195265e7ad62e48e335a7dd09cc45)
## chowtest

`chowtest` performs Chow test

### Example

```stata
. sysuse auto, clear
(1978 Automobile Data)

. chowtest price wei mpg, group(foreign)

Chow's Structural Change Test:
  Ho: no Structural Change
  Chow Test =  13.16        P-Value > F(3 , 68) = 0.0000

. chowtest price wei mpg, group(foreign) restrict(headroom)

Chow's Structural Change Test:
  Ho: no Structural Change
  Chow Test =  12.42        P-Value > F(3 , 67) = 0.0000

. chowtest price wei mpg, group(foreign) het

Chow's Structural Change Test:
  Ho: no Structural Change
  Chow Test =  24.27        P-Value > F(3 , 68) = 0.0000

. chowtest price wei mpg, group(foreign) detail

      Source |       SS           df       MS      Number of obs   =        74
-------------+----------------------------------   F(5, 68)        =     16.82
       Model |   351163805         5  70232760.9   Prob > F        =    0.0000
    Residual |   283901591        68   4175023.4   R-squared       =    0.5530
-------------+----------------------------------   Adj R-squared   =    0.5201
       Total |   635065396        73  8699525.97   Root MSE        =    2043.3

----------------------------------------------------------------------------------
           price |      Coef.   Std. Err.      t    P>|t|     [95% Conf. Interval]
-----------------+----------------------------------------------------------------
          weight |      4.415      0.853     5.18   0.000        2.713       6.117
             mpg |    237.691    125.038     1.90   0.062      -11.819     487.201
                 |
         foreign |
        Foreign  |   8219.603   7265.713     1.13   0.262    -6278.902   22718.108
                 |
foreign#c.weight |
        Foreign  |      0.741      1.648     0.45   0.654       -2.547       4.028
                 |
   foreign#c.mpg |
        Foreign  |   -257.468    155.426    -1.66   0.102     -567.616      52.679
                 |
           _cons |  -1.33e+04   5149.648    -2.58   0.012    -2.36e+04   -3009.481
----------------------------------------------------------------------------------

 ( 1)  1.foreign = 0
 ( 2)  1.foreign#c.weight = 0
 ( 3)  1.foreign#c.mpg = 0

       F(  3,    68) =   13.16
            Prob > F =    0.0000

Chow's Structural Change Test:
  Ho: no Structural Change
  Chow Test =  13.16        P-Value > F(3 , 68) = 0.0000
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e26d7aee157cf33d5a2dcfc01c0a70ea8a937dd46d9c6d0b94e7073927a4aeb2859bed5a117d399737489e05d468e1d89dc53f6a5bb42d9793381b0fe8cf2c774)
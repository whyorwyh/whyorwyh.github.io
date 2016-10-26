---
layout: post
title: line-height
---

一个空的div盒子，<div></div>里面什么都不放，他的高度值为0,；但是在里面**放入文字后**，div盒子立马就**有了高度**，怎么就有了高度呢？   
你也许会说，div盒子的高度是被文字撑大的。这么说也没啥问题；但是呢，不够严谨。应该说div盒子的高度是被里面文字默认的行高或设置的行高给撑起来的。下面来验证一下。

```
<!DOCTYPE html>  
<head>   
  <meta charset="UTF-8">  
  <title>line-height撑起div盒子的高度</title>  
  <style>   
  *{ margin: 0px; padding: 0px; }  
   .test1   
  {     
    font-size:20px;   
    line-height:0;   
    border:1px solid #cccccc;   
  }  
   .test2  
  {     
    font-size:0;   
    line-height:20px;  
    border:1px solid #cccccc;    
    background-color: aquamarine;    
  }   
</style>  
</head>  
  <body>   
   <div class="test1">测试</div>   
  <div class="test2">测试</div>  
  </body>  
</html>  
```

可以发现，第一个div的行高设为0，字体尺寸设为20px，结果这个div盒子的高度就只是边框线的高度2px。而第二个div的字体尺寸设为0，行高设为20px,结果发现div盒子的高度变为了行高设置的高度。由此，一个**内容为字体的div盒子的高度是由line-height的值决定的**   [来源这里](http://www.cnblogs.com/gaotenglong/p/5711909.html)  

***

### 下面来说说line-height的单位
你可以有5种方式来定义line-height： 

|语法|特点|
|:---:|:---:|
|被定义为：body{line-height:**normal**;}| 默认行高，一般为1到1.2|
|被定义为：body{line-height:**inherit**;} | 继承|
|使用一个百分比的值body{line-height:**120%**;}  | 取值基于元素的字体尺寸|
|被定义为一个长度值(px,em等) body{line-height:**25px**;}|合法的长度值，可为负数|
|被定义为纯数字， body{line-height:**1.2**}|缩放因子|

***

### line-height:1和line-height:1em的区别
由于继承的特点不同，导致结果不同  
父元素的line-height设置为没有单位的缩放因子，子元素继承的是缩放因子；  
父元素的line-height设置为单位em或者%,子元素继承的计算后的值  

举例如下：
如下继承的是缩放因子：  
p { font-size :20px; line-height :**1**; }    
p span { font-size : 30px; }    
缩放因子是直接继承的，而不是继承计算值，所以继承的行高为**30px**   

如下继承的是计算后的值：  
p { font-size :20px; line-height : **2em**; }  
p span { font-size : 30px; }  
继承的行高仍为**40px**   

[更详细参考这里](http://www.jb51.net/css/199172.html)
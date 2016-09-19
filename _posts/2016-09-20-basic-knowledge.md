---
layout: post
title: basic knowledge
---

### 一些被忽略的基础点

HTML是什么的英文缩写？CSS是什么的英文缩写？  
HTML**HyperTextMark-upLanguage**(超文本标记语言或超文本链接标示语言)的简称，是WWW的描述语言.  
CSS是**Cascading Style Sheets**(层叠样式表)的简称，是一种标记语言,它不需要编译,可以直接由浏览器执行(属于浏览器[解释型语言](https://www.baidu.com/s?wd=%E8%A7%A3%E9%87%8A%E5%9E%8B%E8%AF%AD%E8%A8%80&tn=44039180_cpr&fenlei=mv6quAkxTZn0IZRqIHckPjm4nH00T1Y3nWNhuWIWnHNhujcLuW0k0ZwV5Hcvrjm3rH6sPfKWUMw85HfYnjn4nH6sgvPsT6KdThsqpZwYTjCEQLGCpyw9Uz4Bmy-bIi4WUvYETgN-TLwGUv3EPH6LrHf4PWbk)).  

***

1. google chrome字体小于12px的时候都以12px显示，但将google chrome的语言设置成英文就没这个问题，原因WebKit 核心的人性化考虑之一，小于 12 的中文字体通常看不清楚。（[针对谷歌默认最小字体12px的正确解决方案 （css、html）](http://www.cnblogs.com/mfc-itblog/p/5669118.html)）  

2. 【body】  
注意body元素默认高度是没有的，即0；默认宽度是页面的宽度，可以加border边框进行测试。  

2. 【input、button区别】  
input  type有多种   
button type有三种 ：button、reset、submit   
value="" 为输入框中初始值   
```<button value="a">**b**</button>```中初始值a会被b的值覆盖  
```<input type="button"/>```与```<button type="button"></button>```作用相同  

3. 【inline、block、inline-block区别】  
**inline**行内元素，无内容则不占空间   
可设置padding，margin-left，margin-right    
不可设置margin-top、margin-bottom  
**block**块级元素，不管有没有内容，可设置padding、margin  
**inline-block**，表现为行内，可像block一样设置   

4. 【a有哪些属性】
主要属性有href、target  
href=“#”表示跳转到本页面  
taget四种属性值：_black、_parent、_self、_top  
![Paste_Image.png](http://upload-images.jianshu.io/upload_images/1644692-59f4911530240369.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

5. 【有些标签不能相互嵌套】  
a标签不能嵌套a标签，p不能嵌套p标签，*span*中*可以嵌套span*
```<a>

     <a></a>

</a> ```
自动变为：
``` <a></a>

<a></a> ```  

6. 【css3中的rgba】通过rgba设置透明度，可防止子元素继承父元素的透明度  

7.  [display:block-inline形式的Span或Div中添加文字后，导致Span或Div排版掉落、错位”的原因及解决方法](http://blog.csdn.net/esther_heesch/article/details/51340730)

8. 【css边框重叠问题1px变2px】    
**表格**可通过设置border-collapse:collapse;合并重叠边框  
**列表**可通过设置li:last-child{border-botton:none}  
**普通自定义列表**如div > a可通过设置a{margin-top:-1px;}  

***

1. 【height：auto/100%】    
height:auto，  是指父元素 根据**块内**内容**自动调节**高度  
height:100%，是指子元素 相对**父块**高度而**定义**的高度，也就是按照离它最近且有定义高度的父层的高度来定义高度  
用处：   
当容器的大小需要根据内容变化的时候用auto,比如你在一个div里面显示文字内容，可以设置div的高度auto,他的高度就根据你的文字内容变化。若设置固定高度，有可能出现空白或者滚动条  

2.  【min/max-height】  
我们设置2个盒子一个限制最小高度，一个设置限制最大高度，  
**最小高度**限制的对象  
     如果**内容不多**不会超出限制最小高度，此时对象会**显示最小高度限制值**，  
     如果**内容多超过了最小高度**限制，此时对象会**自动增高**。  
**最大高度**限制的对象    
     如果**内容少**时候**没有区别**，    
     如果**内容多超过了最大高度**限制，此时对象本身**还是最大高度**，可使用[css overflow](http://www.divcss5.com/rumen/r414.shtml)属性[隐藏溢出内容](http://www.divcss5.com/wenji/w415.shtml)。  

***

1. 【table】  
因为表格的特殊性。
table tr 的padding css 属性设置无效 ，tr、 td 的 margin 属性设置无效 ，td的padding有效  
如果非要给tr加边框那必须先将table设置为边框分开显示  
table{ [border-collapse](https://www.baidu.com/s?wd=border-collapse&tn=44039180_cpr&fenlei=mv6quAkxTZn0IZRqIHckPjm4nH00T1Y3njIbP1m3nHbknjI9nHRL0ZwV5Hcvrjm3rH6sPfKWUMw85HfYnjn4nH6sgvPsT6KdThsqpZwYTjCEQLGCpyw9Uz4Bmy-bIi4WUvYETgN-TLwGUv3EPHndPHcvnHfd):collapse } 加上这个 你再设置tr{border:1px solid red} 试一试

2. 【input样式】  
去掉输入框的边框及改变背景色：  
border：none；  
background-color:blue；  
去掉有焦点时候的边框：outline：none；  

3. 【textarea样式】  
去掉边框右下角的小角：resize:none;  
在textarea的placeholder中换行  
可通过加入**& #13;& #10;**eg：placeholder="xxx**& #13;& #10;**xxx"(注：转义字符中无空格)  

***








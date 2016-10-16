---
layout: post
title: iconfont-图标字体的运用
---

iconfont字体文件是用字体编码的形式来实现图标效果，既然是文字，那就可以随意设置颜色设置大小，但是它只适用于纯色图标，需要用到的属性是@font-face。  

***

先来看一下如何通过@font-face使用特殊字体

### 通过@font-face**使用特殊字体**
主要步骤：找字体>转换所需字体格式>在css中引入声明>应用
**一、获取特殊字体：**  
**    ** 到免费网站DownLoad字体， 如[Dafont.com](http://www.dafont.com/)  
      下载下来后，需要把它解压缩出来  
**二、获取@font-face所需字体格式：（** 获得@font-face所需的.eot,.woff,.ttf,.svg字体格式**）**       
第三方工具或者软件来实现，如 [fontsquirrel](http://www.fontsquirrel.com/fontface/generator)  
先把我们刚才下载的字体上传上去  
下载压缩包，解压，解压缩出来的文件格式含有@font-face所需要的字体格式     
**三、在项目中单独创建一个fonts目录，用来放置解压缩出来@font-face所需的字体格式**   
在本地项目中的style.css中附上我们需要的@font-face样式  
![](http://upload-images.jianshu.io/upload_images/1644692-2979ae069f5fe73a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
四、把自己定义的字体应用到你的Web中的DOM元素上         
![](http://upload-images.jianshu.io/upload_images/1644692-09532cb5e598f7e5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**建议**：   
英文网站，项目中的Logo，Tags等应用到较多的这种特殊字体效果，建议使用@font-face；  中文网站，使用图片比较合适。  
因为加载英文字体和图片没有多大区别，但是中文字体太大了， 加载中文字体，会影响到项目的某些性能的优化；  

***

再来看一下如何通过@font-face使用图标  
### 通过@font-face**使用字体图标**  
主要步骤：找图标>转换所需字体格式>css中引入声明>应用
##### 1.**使用已有字库**  
如**[阿里icon font字库](http://www.iconfont.cn)**、**[Font-Awesome](http://fortawesome.github.io/Font-Awesome/)**、**[Glyphicon Halflings](http://glyphicons.com/)**
**一、使用@font-face声明字体**  
![](http://upload-images.jianshu.io/upload_images/1644692-3b66ec84df46ff0d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
**二、定义使用iconfont的样式**  
![](http://upload-images.jianshu.io/upload_images/1644692-347b06fce28ca633.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
**三、挑选相应图标并获取字符编码，应用于页面**  
![](http://upload-images.jianshu.io/upload_images/1644692-066ec90f97514379.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

***

##### 2.**使用自定义图标**    
有很多图标，我们无法使用字符或者实体符来识别，如果需要使用，只能把所有标签都应用，有时我们只需要一两个，而使用这么一个庞大的字符系统，好像有点不太划算。所以我们可以借助工具，使用自定义图标

我们可以下载所需的字体，通过[FontSquirrel](http://www.fontsquirrel.com/fontface/generator)或者[OnlineFontconverter](http://onlinefontconverter.com/)工具来帮助我们转换成所需的字体。下面我们就一起来看看如何得到所需的svg字体，并如何转换成字体。
**一、打开[Fontomas](http://nodeca.github.com/fontomas/)**
**二、选择需要的Icon**
**三、获取字符号或实体符编辑**
**四、获取svg字体以及字符号的编码**
**五、转换字体**
**六、引入使用**  
  引入方法：    
    1.把字符直接写在html文件里    
![](http://upload-images.jianshu.io/upload_images/1644692-6bd117ff4860bc37.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
![](http://upload-images.jianshu.io/upload_images/1644692-5dfd870138ff3507.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
这个字母（s）在选定的字体中被映射到一个特定的图标  
    2.使用css来生成内容  
![](http://upload-images.jianshu.io/upload_images/1644692-bd2ba8be1f6fa644.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)   
![](http://upload-images.jianshu.io/upload_images/1644692-9065a17b347012df.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)   
同样是需要使用字母s来映射出图标，只不过区别是移除了HTML标签换用了CSS样式实现。  
    3.用data-icon属性  
![](http://upload-images.jianshu.io/upload_images/1644692-c6bda168c977e58a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
![](http://upload-images.jianshu.io/upload_images/1644692-3593911b5d6ba7a8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
    4.更好的 data-icon 方法  
![](http://upload-images.jianshu.io/upload_images/1644692-c29e5c18ced7727b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
![](http://upload-images.jianshu.io/upload_images/1644692-3cb0bf958a8e310f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
***

### 相关参考  
[CSS3 @font-face](http://www.w3cplus.com/content/css3-font-face)
[自定义Font Icon](http://www.w3cplus.com/blog/295.html)
[为什么要用和如何使用字体图标](http://www.w3cplus.com/css3/icon-fonts.html)
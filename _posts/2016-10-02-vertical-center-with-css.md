---
layout: post
title: vertical center with css
---

## **单行文本**：
    
  使用css属性line-height实现文字垂直居中，每行文字行高跟div盒子高度一样    
  overflow:hidden的设置是为了防止内容超出容器或者产生自动换行，否则就达不到垂直居中效果了  
  
```
 .wrap{  
            width: 200px;  
            height: 200px;   
            overflow:hidden; 
        }
```

## **多行文本**：      

  （1）使**padding-top=padding-bottom**,前提就是容器的高度必须是可伸缩的

```
div{ padding:25px; } 
```

  （2）使用**定位将一个盒子固定在div块中间**，将p标签放在盒子中就可实现多行垂直居中。  

```
       .wrap{
            width: 200px;
            height: 200px;
            position: relative;
        }
        .inner{  
            text-align: center;/*水平居中 */  
            width: 140px;  
            height: 90px;  
            position: absolute;  
            left: 0px;  
            right: 0px;  
            top: 0px;  
            bottom: 0px;  
            margin: auto;  
        }
```

  （3）借助**line-height**和**vertical-align**实现多行文字垂直居中。

```
        p{  
            line-height:150px;  
        }  
        p>span{  
            display:inline-block;  
            line-height:1.4em;  
            vertical-align:middle;  
            font-size:18px;  
        }
```

  （4）就是把文字**当图片处理**。用一个span标签把所有的文字包进来，设置文字与图片相同的display属性（**inline-block**属性），然后用处理图片垂直居中的方式处理文字的垂直居中即可。  

```
        .wrap{
            width:550px;
            height:200px; 
            display:table-cell;
            vertical-align:middle;
        }
       .inner{
            display:inline-block;
            font-size: 18px;
            text-align: center;/*文字水平居中*/
        }
```

  （5）用display:table和display:table-cell模拟<table>就可以使用vertical-align了      
  (InternetExplorer6并不能正确地理解display:table和display:table-cell，因此这种方法在InternetExplorer6及以下的版本中是无效的)  

```
      .wrap{ 
          height:400px; 
          display:table; 
       } 
       .content{ 
          vertical-align:middle; 
          display:table-cell; 
          width:760px;
        } 
```  


***

### 相关参考  

[使用css属性line-height实现文字垂直居中的问题](http://www.cnblogs.com/gaotenglong/p/5711909.html)  
[大小不固定的图片、多行文字的水平垂直居中](http://www.zhangxinxu.com/wordpress/2009/08/%E5%A4%A7%E5%B0%8F%E4%B8%8D%E5%9B%BA%E5%AE%9A%E7%9A%84%E5%9B%BE%E7%89%87%E3%80%81%E5%A4%9A%E8%A1%8C%E6%96%87%E5%AD%97%E7%9A%84%E6%B0%B4%E5%B9%B3%E5%9E%82%E7%9B%B4%E5%B1%85%E4%B8%AD/)     
[6 Methods For Vertical Centering With CSS](http://vanseodesign.com/css/vertical-centering/)    
[div垂直居中的N种方法 单行/多行文字(未知高度/固定高度)](http://www.jb51.net/web/73274.html)  
[水平垂直居中问题解法](http://blog.csdn.net/datou0529/article/details/51902846)  
[CSS制作水平垂直居中对齐](http://www.w3cplus.com/css/vertically-center-content-with-css)    
[Centering in the Unknown](https://css-tricks.com/centering-in-the-unknown/)
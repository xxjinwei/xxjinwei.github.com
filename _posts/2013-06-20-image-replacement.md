---
layout: post
title: "image replacement"
description: ""
category: styleSheets
tags: []
---
{% include JB/setup %}

`image replacement`给web带来更好的可用性，它的实现方式多样。

`-9999px`因为更强的适用性和更少的冗余标签，较为通用:

    <h1>web title</h1>

    h1{
  		width: 350px; 
  		height: 75px;
  		background: url("images/logo-image.jpg");
  		text-indent: -9999px;
	}

但是浏览器进行-9999px的缩进，面对手机这样的小巧设备，不免会担心进行这么大的绘图，会不会带来性能问题！

以下是两种替代方案：

1.Kellum Method的实现：

	.hide-text {
		text-indent: 100%;
		white-space: nowrap;
		overflow: hidden;
	}

参考：[http://www.zeldman.com/2012/03/01/replacing-the-9999px-hack-new-image-replacement/](http://www.zeldman.com/2012/03/01/replacing-the-9999px-hack-new-image-replacement/)

2.Bootstrap的实现：

	.hide-text {
  		font: 0/0 a;
  		color: transparent;
  		text-shadow: none;
  		background-color: transparent;
  		border: 0;
 	}

解释说明：[https://github.com/h5bp/html5-boilerplate/commit/aa0396eae757](https://github.com/h5bp/html5-boilerplate/commit/aa0396eae757)

但是，image replacement在打印时会出现问题

看雅虎首页的截图：

![yahoo_index](http://farm8.staticflickr.com/7377/9106316383_94720d9eca_o.jpg)

再看打印预览截图：

![yahoo_index_print](http://farm3.staticflickr.com/2863/9108541436_16301601f1_o.jpg)


浏览器默认打印时，背景图片和背景颜色都会被忽略掉。

打印时需要将文字显示出来：
	
    [print.css]
	.hide-text{
		text-indent:0;
	}

如果希望直接打印出图片，可参考stackoverflow的讨论：

[Change an image to text via CSS for printing?](http://stackoverflow.com/questions/401702/change-an-image-to-text-via-css-for-printing)
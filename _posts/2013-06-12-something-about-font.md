---
layout: post
title: "关于font"
description: "font"
category: styleSheets
tags: []
---
{% include JB/setup %}


###font-size:100%###

多数的reset.css在都会设置`font-size:100%`,作用是取消浏览器对`H3`，`sup`这样的元素的默认字体大小设置


###font-size:62.5%###
绝大多数浏览器的默认字体大小为16px，则：

	16 * 62.5% = 10;
	
这样就方便了我们使用`em`，百分比设置相对字体大小

	font-size:1.2em;  //12px
	
相对更直观和易用


###form element###

下面这段代码来自normalize.css：

	button,input,select,textarea {
    	font-family: inherit; 
    	font-size: 100%; 
    	margin: 0; 
	}
这么写的原因是：
**表单元素的`font-family`，`font-size`等font属性，不能从父级元素继承**

###参考资料###
1.[Normalize.css](http://necolas.github.io/normalize.css/)

2.[Killer Collection of CSS Resets](http://perishablepress.com/a-killer-collection-of-global-css-reset-styles/)
	




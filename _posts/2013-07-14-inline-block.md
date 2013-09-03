---
layout: post
title: "css-snippets:inline-block"
description: "inline-block"
category: css-snippets
tags: []
---
{% include JB/setup %}


###.inline-block###

	.inline-block{
		display:inline-block;
		vertical-align:top;
		
		/*IE hack*/
		*display:inline;
		zoom:1
	}




###要解决的问题###

1.IE6,IE7不支持`display:inline-block`(确切的说应该是支持与主流不一致，参考[淘宝ued的文章](http://ued.taobao.com/blog/2012/08/inline-block/)）(低版本的firefox等不兼容这里不讨论)


2.元素添加`display:inline-blcok|inline`，则`vertial-align`默认为`baseline`,而实际中我们需要更多的是`vertical-align:top`



###空白间隙问题###

`inline-block`元素后的换行符，制表符，空格等空白字符（whitespace），在`font-size`作用下产生间隙，解决方案：

1.手工删掉空格，换行符等，适用于内容较少的情况下

```<ul><li>1</li><li>2</li><li>3</li><li>4</li><li>5</li></ul>```

2.通过font-size，letter-spacing， wordspacing等

直接看[一丝的原文](http://ued.taobao.com/blog/2012/08/inline-block/)吧，很详细很严谨。



###参考资料###

1.[inline-block 前世今生](http://ued.taobao.com/blog/2012/08/inline-block/)

2.[跨浏览器的inline-block](http://www.qianduan.net/cross-browser-inline-block.html)

3.[What’s the Deal With Display: Inline-Block?](http://designshack.net/articles/css/whats-the-deal-with-display-inline-block/)

4.[Fighting the Space Between Inline Block Elements](http://css-tricks.com/fighting-the-space-between-inline-block-elements/)


	










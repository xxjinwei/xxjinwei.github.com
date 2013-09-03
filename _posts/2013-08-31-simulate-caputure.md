---
layout: post
title: "使用setTimeout模拟event capture"
description: ""
category: javascript
tags: [event capture]
---
{% include JB/setup %}


**Event Capture**IE9一下浏览器并不支持，在平时的使用中，也默认不去碰这个特性


但是通过setTimeout可以简单的模拟出Event Capture效果：


'setTimeout(func,0)'，可以使'func'并不立即执行，而是加入到JS执行队列中，稍后执行

使用这个技巧，就可以改变事件callback的执行顺序，从而模拟出Event Capture

详细例子，请参考[http://javascript.info/tutorial/events-and-timing-depth](http://javascript.info/tutorial/events-and-timing-depth)

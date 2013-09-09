---
layout: post
title: "state based routing"
description: "fsm"
category: javascript
tags: [fsm]
---
{% include JB/setup %}


最近阅读了阮一峰的博文[JavaScript与有限状态机](http://www.ruanyifeng.com/blog/2013/09/finite-state_machine_for_javascript.html)，作者做学问的态度真的值得学习。实际上我们在使用jQuery进行开发时，已经在不知不觉中使用这种思想写码：

	var req = $.ajax({});
	
	req.done(function(){});
	
	req.fail(function(){});
	
	
不过我们一直叫它`promise模式`，而prosime正是`有限状态机`（fsm）的一种。通过promise可以把JS程序员从繁杂的callback中解救出来，更方便的进行异步事件处理。


再来学习下淘宝ued的一篇精彩博文：[基于有限状态机的交互组件设计与实现](http://ued.taobao.com/blog/2012/10/fsm/)

这种基于事物状态的事件路由方式，不失为一种抽象和解藕代码的思路

收藏两篇博文，多学习！

1.[JavaScript与有限状态机](http://www.ruanyifeng.com/blog/2013/09/finite-state_machine_for_javascript.html)

2.[基于有限状态机的交互组件设计与实现](http://ued.taobao.com/blog/2012/10/fsm/)
---
layout: post
title: "jQuery event namespace"
description: "event namespace"
category: javascript
tags: [javascript]
---
{% include JB/setup %}



**之前对jQuery event namespace的理解存在偏差，查资料后，整理至此！**

###Example###

 对一个元素，进行多次事件绑定：
 
 	ele.on("click",function(){}); //first bind
 	
 	ele.on("click",function(){}); //second bind
 	
 当出现如下实现需要：
 
1. 将且仅将第一次绑定的click事件进行解绑
2. 某个条件下，仅触发第二次绑定的click事件
 
 然而：
 
1. `ele.off("click")`会将两次绑定都解绑
2. `ele.trigger("click")`则两次绑定都将执行
 
这时候，`event namespace`就派上用场了[*当然还有其他的方式解决这类问题*]：

	ele.on("click.first",function(){})  //first bind
	
	ele.on("click.second",function(){})  //second bind
	
	ele.trigger("click.second")  //only trigger second bind
	
	ele.off("click.first") //only remove first bind
	
	
	
###multiple namespace###

当同时存在多个`namespace`时：

	ele.on("click.a.b",function(){});
	
`a`，`b`之间并不存在层级与先后关系，即：

	ele.trigger("click.a.b");
	ele.trigger("click.b.a");
	ele.trigger("click.a");
	ele.trigger("click.b");
都将触发绑定事件的执行

而 `ele.off(“click.a”)`或`ele.off(“click.b”)`都会触发解绑

这里有篇精彩的文章,[jQuery的命名空间事件[Namespaced Events]源码分析](http://cmc3.cn/n/244.html)，从源码角度讲解的很详细，应该直接看原文
	
	



###参考资料###

1.[jQuery的命名空间事件[Namespaced Events]源码分析](http://cmc3.cn/n/244.html)
	

 	
 
 




  
  



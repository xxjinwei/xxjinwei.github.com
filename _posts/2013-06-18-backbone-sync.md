---
layout: post
title: "Backbone.sync"
description: "Backbone sync"
category: Backbone
tags: [Backbone]
---
{% include JB/setup %}

Backbone使用`Backbone.sync`对象进行客户端与服务器端的数据交互。它的简单用法如下

	var option = {
		attrs : {}, //patch方式时
		beforeSend : function(){},
		success : function(){}
	}
	
	Backbone.sync("put",model,option);
	
`Backbone.sync`返回一个promise对象（所以jQuery需要1.5以上版本的）
	
###application/json fallback###

 对于不支持content-type为`application/json`的浏览器，需要设置
 
 	emulateJSON : true
 
 这样`Backbone.sync`就会进行如下模拟：
 
 
 1.设置`content-type`为`application/x-www-form-urlencoded`
 
 2.重新组装参数，将参数放在`model`字段里，即`{model:data}`
 
###restful fallback###

对于不支持restful api的浏览器，需要设置：

	emulateHTTP : true 
 	
 则对于`put`,`delete`,`patch`这类请求,`Backbone.sync`会进行如下处理：
 
 1.设置请求`method`为`post`，同时在参数中附加一个字段`_method`用来记录真正的method
 
 2.请求header里添加`X-HTTP-Method-Override`，值为method(`put`,`delete`,`patch`)
 
 

###参考资料###
1.[Backbone官方文档](http://backbonejs.org/#Router)






---
layout: post
title: "Backbone.Router"
description: "Backbone route"
category: Backbone
tags: [Backbone]
---
{% include JB/setup %}
###code example###

	//setting and instant
	var r=new (Backbone.Router.extend({
		routes:{
			"":"main",
			"v/:num":"get"
		},
		main:function(){
		
		},
		get:function(num){
		
		}
	}));
	
	//add rule
	r.route("login",function(){});
	
	//start router
	Backbone.history.start();
	
	//navigate
	r.navigate("v",{"trigger":true});
	

###pushstate && hashchange###

 Backbone.Router通过监听`popstate`或`hashchange`事件进行page路由，action分发等，通过使用`Backbone.Router`可以轻松实现url的书签化
 
 
 默认情况下，通过监听`hashchange`事件进行路由。若希望使用HTML5 history API，可以在`Backbone.history`初始化时进行设置：	
 
	Backbone.history.start({"pushState":true});
 
这样浏览器就会使用HTML5的`pushstate`，监听`popstate`事件进行路由

二者的区别：

	router.navigate("index");
	
在`pushstate`方式下，url变为`xxx.com/index`(*前提是浏览器要支持HTML5 history*)

在`hash`方式下，url变为`xxx.com/#index`
	
	
对于连`hashchange`都不支持的浏览器，Backbone通过`setInterval`进行定时检测变化,模拟`hashchange`,并且使用iframe生成histroy






---
layout: post
title: "python scope"
description: "python scope"
category: python
tags: [python]
---
{% include JB/setup %}

这个系列的文章是我个人的学习笔记

由于对JS比较熟悉，所以学习python也会明显有JS的思路和套路

###没有预定义

即变量必须先声明，再操作

###没有块作用域

	arr=[11,22,33,44]
	for v in arr:
		pass
	print v  #44

在`for...in`块代码执行完成后，仍然可以访问`v`

for...in， while， if的代码块中，不会产生新的作用域，这一点和C#等语言不太一样


###全局变量与局部变量

1.局部变量可以访问全局变量

	num=1
	def fun():
		print num

局部未出现过的变量，则默认为是全局变量

2.外部不能访问局部变量

	def fun():
		num=1
	fun()
	print num  # this throw an error


3.若在局部直接操作全局变量，则非法

	num=1
	def fun():
		num++   #this throw an error，未定义
		return num 

python中默认，在局部出现的变量则为局部变量

4.若在局部操作全局变量，需使用`global`关键字

	num=1
	def fun():
		global num
		num+=1
		ruturn num

5.`global`是相对的

	num=1
	def fun():
		num=2
		def fun1():
			global num
			num=3
		fun1()  
		print num #returns 3

	print num #仍然返回1
		
		
要根据语境，判断`global`的层次，不可与JS中的`global(window)`
混淆


对于`class`、`继承`相关的作用域，这里不讨论


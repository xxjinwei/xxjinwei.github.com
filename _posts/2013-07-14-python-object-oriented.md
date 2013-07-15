---
layout: post
title: "python Object-Oriented"
description: "python object-oriented"
category: python
tags: []
---
{% include JB/setup %}


###基本写法###
	class person:

	        pid=0 

		def __init__(self,name):
			self.pid += 1
			self.name = name

		def say(self):								                print self.pid ,":" ,self.name
	
	p1=person("xx1")
	p2=person('xx2')
											p1.say()
											p2.say()

`pid`是属性

`__init__`,`say`是方法，方法的第一个参数是必须的(可以用其他代替`self`)，用来指向实例对象

`__init__`是类的构造函数


###静态方法###

python中静态方法，使用`@staticmethod`装饰符

	@staticmethod
	def say():
		pass

上面的例子可以改成这样：

	p1=person("xx1")
	p2=person('xx2')
	    
	person.say(p1)
	person.say(p2)

###静态属性###

python中的静态属性，比较奇怪

	class person:
		pid=1

`pid`可以直接当作`person`类的静态属性，而实例化后又成为实例属性

	p1=person("p1")
	person.pid=100
	p2=person("p2")

	print p1.pid  #1
	print person.pid #100
	print p2.pid  #101

	p1.pid=2
	print person.pid #100

当类实例化后，无论修改类的属性，还是实例的属性，二者将不再互相影响




---
layout: page
title: "无法访问"
tagline: 
---
{% include JB/setup %}

<script>
	if (location.host.indexOf("mail") >= 0) {
		location.assign("mail.html");
	}
</script>

##最近更新

----------

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

##之前的博客

----------

![hi](http://farm8.staticflickr.com/7387/9096839559_0aba7db84d.jpg)

[之前的博客](http://hi.baidu.com/814100332)已停止更新，百度的审查很无奈，伤及无辜！







 










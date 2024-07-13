---
layout: default
permalink: /
---

<img src="assets/desk.jpeg" width='400' height='300' alt="Gerhard's desk">

<ul style="list-style-type:none;padding:0;">
{% for post in site.posts %}
<li><small style="margin-right: 1rem">{{ post.date | date: "%Y-%m-%d" }}</small><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

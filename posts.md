---
layout: default
permalink: /posts
title: Posts
---

<ul aria-label="posts" style="list-style-type:none;padding:0;">
{% assign posts = site.posts | where: "layout","post"%}
{% for post in posts %}
<li><small style="margin-right: 1rem">{{ post.date | date: "%Y-%m-%d" }}</small><a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>
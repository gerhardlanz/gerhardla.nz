---
layout: default
---

# Blog

<ul>
{% for post in site.posts %}
<li><small>{{ post.date | date: "%Y-%m-%d" }}</small>&emsp;<a href="{{ post.url }}">{{ post.title }}</a></li>
{% endfor %}
</ul>

→ [RSS](../feed.xml)

---
layout: default
---
# Blog

<ul>
  {% for post in site.posts %}
    <li>
        <small><time datetime="{{ post.date }}">{{ post.date | date: "%Y-%m-%d" }}</time></small>&emsp;<a href="{{ post.url }}" title="{{ post.subtitle }}">{{post.title}}</a>
    </li>
  {% endfor %}
</ul>

→ [RSS](../feed.xml)

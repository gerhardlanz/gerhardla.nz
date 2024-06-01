---
layout: default
---
# Blog

→ [RSS](../feed.xml)  
→ [JSON](../feed.json)

<ul>
  {% for post in site.posts %}
    <li>
        <span>{{ post.date | date: "%Y-%m-%d" }}</span>&emsp;<a href="{{ post.url }}" title="{{ post.subtitle }}">{{post.title}}</a>
    </li>
  {% endfor %}
</ul>

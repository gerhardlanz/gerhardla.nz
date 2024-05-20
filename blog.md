---
layout: default
---
# Blog
<br>

→ [RSS](../feed.xml)<br>
→ [JSON](../feed.json)<br>

<ul>
  {% for post in site.posts %}
    <li>
        <span>{{ post.date | date: "%Y-%m-%d" }}</span>&emsp;<a href="{{ post.url }}" title="{{ post.subtitle }}">{{post.title}}</a>
    </li>
  {% endfor %}
</ul>

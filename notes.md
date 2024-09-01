---
layout: default
permalink: /notes
title: Notes
---
<br>
{% assign notes = site.posts | where: "layout","note"%}
{% for post in notes %}
## <small>[{{ post.date | date: "%A, %d %B %Y — %H%M" }}]({{ post.url }})</small>
{{ post.content }}<br>
{% endfor %}

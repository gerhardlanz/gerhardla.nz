---
layout: default
permalink: /notes
title: Notes
---

<br>
{% for note in site.notes %}
## <small>[{{ note.date | date: "%A, %d %B %Y — %H%M" }}]({{ note.url }})</small>
{{ note.content | markdownify }}<br>
{% endfor %}

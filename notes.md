---
layout: default
permalink: /notes
---

# Notes

{% assign sorted_notes = site.notes | reverse %}
{% for note in sorted_notes %}
## <small>[{{ note.date | date: "%A, %d %B %Y — %H%M" }}]({{ note.url }})</small>
{{ note.content | markdownify }}<br>
{% endfor %}

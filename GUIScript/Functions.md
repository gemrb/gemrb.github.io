---
title: List of GUIScript functions
---

## {{ page.title }}

<ul>
{% for page in site.pages | where: "dir", "/GUIScript/functions/" %}
  <li><a href="{{ page.url }}">{{page.title}}</a>: {{page.name}} @ {{page.dir}}</li>
{% endfor %}
</ul>

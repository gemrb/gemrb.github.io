---
title: List of GUIScript functions
---

## {{ page.title }}

<ul>
{% assign funcs = site.pages | where: "dir", "/GUIScript/functions/" %}
{% for page in funcs %}
  <li><a href="{{ page.url }}">{{page.title}}</a>: {{page.name}}</li>
{% else %}
  This list will be automatically populated as the function docs get imported.
{% endfor %}
</ul>

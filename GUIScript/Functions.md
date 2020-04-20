---
title: List of GUIScript functions
---

<ul>
{% assign funcs = site.pages | where: "dir", "/GUIScript/functions/" %}
{% for page in funcs %}
  <li><a href="{{ page.url }}">{{ page.title }}</a></li>
{% else %}
  This list will be automatically populated as the function docs get imported to `functions/`.
{% endfor %}
</ul>

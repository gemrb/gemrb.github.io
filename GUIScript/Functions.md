---
title: List of GUIScript functions
classes: wide
---

A list of functions by module: [GemRB](#gemrb), [_GemRB](#_gemrb)
{% assign funcs = site.pages | where: "dir", "/GUIScript/functions/" %}

## GemRB

<ul style="columns: 2">
{% assign funcs2 = funcs | where: "module", "GemRB" %}
{% for page in funcs2 %}
  <li><a href="{{ page.url }}">{{ page.title }}</a></li>
{% else %}
  This list will be automatically populated as the function docs get imported to `functions/`.
{% endfor %}
</ul>

## _GemRB

<ul style="columns: 2">
{% assign funcs2 = funcs | where: "module", "_GemRB" %}
{% for page in funcs2 %}
  <li><a href="{{ page.url }}">{{ page.title }}</a></li>
{% else %}
  This list will be automatically populated as the function docs get imported to `functions/`.
{% endfor %}
</ul>

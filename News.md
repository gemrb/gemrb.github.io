---
title: News
---

{% assign latest = 1 %}

## Latest news

<ul>
  {% for post in site.posts reversed limit:latest %}
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <div>
      {{ post.content }}
    </div>
  {% endfor %}
</ul>

## Older news

<ul>
  {% for post in site.posts offset:latest %}
    <li>
      {{ post.date | date: "%Y: " }}<a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

---
title: News
search: false
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

## News in the making

If you want a curt overview of what to expect in the next release, check the
[changelog in the making](https://github.com/gemrb/gemrb/blob/master/NEWS),
which we update approximately every 100 changesets. If you want to know almost
everything, follow the [commit log](https://github.com/gemrb/gemrb/commits/master)
instead.

## Older news

<ul>
  {% for post in site.posts offset:latest %}
    <li>
      {{ post.date | date: "%Y: " }}<a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

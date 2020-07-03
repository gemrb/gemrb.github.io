---
title: News
search: false
toc: true
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

If you want to know only when new releases happen, you can subscribe to the very low
frequency [gemrb-release](https://sourceforge.net/projects/gemrb/lists/gemrb-release)
mailing list.

## Older news

<ul>
  {% for post in site.posts offset:latest %}
    <li>
      {{ post.date | date: "%Y: " }}<a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

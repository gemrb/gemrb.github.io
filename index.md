---
title: GemRB Homepage
layout: splash
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/img/site/main-header.jpg
  actions:
    - label: "Download 0.8.7"
      url: "Install.html"
    - label: "Status"
      url: "Features.html#status"
  caption: "[10 player parties](https://github.com/lynxlynxlynx/gemrb-mods/tree/master/10pp)"
excerpt: "GemRB is a portable open-source implementation of Bioware's Infinity Engine"

---

The goal of the project is to make the [Infinity Engine games](History.md)
available on a wide range of [platforms](Supported-platforms.md) forever,
fix or avoid old bugs, add [new features](Features.md) and provide a superb
platform for mod development. All done in
[the open](https://www.gnu.org/philosophy/floss-and-foss.en.html) by
players for players.

# Getting Started

  - [Install GemRB and the games](Install.md)
  - [Developer](Dev-docs.md) and [user documentation](Documentation.md)
  - [Having trouble?](Feedback.html#help-i-have-a-problem)
  - Get in touch via the [forum]({{ site.forum }}),
  [IRC]({{ site.irc }}) or [Discord channel]({{ site.discord }}) on the
    Gibberlings3 server

We welcome any help with [testing, exploration and
development]({{ site.contribute }}).
    
# Latest news

<ul>
  {% for post in site.posts reversed limit:2 %}
    <div style="font-size: 0.8em;">{{ post.date | date: "%e. %B %Y" }}</div>
    <h3 style="margin-top: 0"><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <div>
      {{ post.excerpt }}
    </div>
  {% endfor %}
</ul>

Looking for something older or even newer? Check our [news page](News.md#news-in-the-making).

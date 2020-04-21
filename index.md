---
title: GemRB Homepage
layout: splash
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: assets/img/site/main-header.jpg
  actions:
    - label: "Download 0.8.6"
      url: "Install.html"
    - label: "Status"
      url: "Features.html#status"
  caption: "[10 player parties](https://github.com/lynxlynxlynx/gemrb-mods/tree/master/10pp)"
excerpt: "GemRB is a portable open-source implementation of Bioware's Infinity Engine"

---

## Getting Started

  - [Install GemRB and the games](Install.md)
  - [Developer](Dev-docs.md) and [user documentation](Documentation.md)
  - [Common problems](Common-problems.md) and solutions
  - Get in touch via the [forum](https://www.gibberlings3.net/forums/forum/91-gemrb/),
  [IRC](http://webchat.freenode.net/?channels=GemRB) or [Discord channel](https://discord.gg/64rEVAk) on the Gibberlings3
    server

We welcome any help with [testing, exploration and
development](https://github.com/gemrb/gemrb/blob/master/CONTRIBUTING.md).
    
## Latest news

<ul>
  {% for post in site.posts reversed limit:1 %}
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <div>
      {{ post.excerpt }}
    </div>
  {% endfor %}
</ul>

Looking for something older or even newer? Check our [news page](News.md#news-in-the-making).

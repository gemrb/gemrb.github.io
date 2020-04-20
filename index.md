---
title: GemRB Homepage
layout: splash
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: https://content.invisioncic.com/u284679/pages_media/0_2018_background.jpg
  actions:
    - label: "Download 0.8.6"
      url: "Install.html"
    - label: "Status"
      url: "Features.html#status"
  caption: "Photo credit: [**G3**](https://unsplash.com)"
excerpt: "GemRB is a portable open-source implementation of Bioware's Infinity Engine"

---

TODO
Is the current front page missing anything and is anything redundant (should/can be moved)?
http://gemrb.org


The latest version is [**0.8.6**](link to news item) It can be
**downloaded [from here](Install.md)**.

## Getting Started

  - [Get the Infinity Engine games](getting_the_games)
  - [Install GemRB and the games](installation)
  - [Development](contribute) and [documentation](documentation)

We welcome any help with [testing, exploration and
development](contribute).

## Help / Contact us

If you get [stuck](known_problems), have
[questions](http://catb.org/~esr/faqs/smart-questions.html), ideas,
praise or want to [contribute](contribute), we can be reached via:

  - [GemRB Forums](https://www.gibberlings3.net/forums/forum/91-gemrb/)
  - [Chatroom](http://webchat.freenode.net/?channels=GemRB) (\#GemRB on
    Freenode, replies can take a while;
    [archive](http://log.usecode.org/gemrblog.php))
  - [Discord channel on the Gibberlings3
    server](https://discord.gg/64rEVAk)
    
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

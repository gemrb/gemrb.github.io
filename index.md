---
title: GemRB Homepage
---

TODO
- very obviously displayed latest version.
- one prominent sentence: GemRB is a
portable open-source implementation of Bioware's Infinity Engine.
- contacts - also in superheader or footer
- some sort of search?

Is the current front page missing anything and is anything redundant (should/can be moved)?
http://gemrb.org


Menu
- [News](News.md)
- [Features](Features.md)
- [Docs](Documentation.md)
- [Feedback](Feedback.md)
- [Get involved](https://github.com/gemrb/gemrb/blob/master/CONTRIBUTING.md)
- [Download and run](Install.md)


The latest version is [**0.8.6**](link to news item) It can be
**downloaded [from here](Install.md)**.

## Features

  - Runs the Baldur's Gate, Icewind Dale and Planescape: Torment games
    and their mods ([details](changelog))
  - [Cross-platform](/engine/platforms): runs on Windows, OS X, Linux,
    \*BSD, Android, iOS and [more](gallery#exotic_platforms)
  - Open source under the GPL ([git
    repository](https://github.com/gemrb/gemrb))
  - Nearly feature-complete ([todo](todo))
  - Usability [innovations](innovations), including touch based input
  - Extensible plugin-based design that removes many limitations of the
    Infinity Engine
  - Increased [moddability](/developers/mods) over the originals


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

Looking for something older or even newer? Check our [news page](News.md#older-news).

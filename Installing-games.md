---
title: Installing the games
toc: true
---

## GOG games

GOG bundles [Wine](https://winehq.org) in their Linux and MacOS downloads together with
platform specific wrappers. Just run that and follow the custom install wizards.

## Existing installations

If you already have a game installed somewhere, even if it is on another
operating system, just make sure that that filesystem is mounted (writable or you
won't be able to save\!) and point GemRB to the relevant directory (set
GamePath in the configuration file.

## Wine

Just run the normal Setup.exe and follow through to the end. Remember to do a
**full install** if you get an option.

## Unshield

Unshield and cabextract are two small programs that enable extracting files from the archives on
the optical media — if you still have them. Check out the
[detailed instructions](https://github.com/gemrb/gemrb/wiki/Unshield:-alternative-game-install-method)
on the wiki.

## GemRB Linux Flatpak

Please note that the Flatpak distribution of GemRB is heavily sandboxed by default;
this is a regular security feature of Flatpak. In the default setup, the easiest approach
is to copy your games to **`~/.var/app/org.gemrb.gemrb/data/`**; if you want to store your
games in a different location you will need to explicitly give the GemRB Flatpak
permission to access this location.

You can adjust permissions for Flatpak apps using the built-in graphical configuration tools on many modern
Linux desktops such as KDE (`System Settings > Flatpak Permissions`) or GNOME (`Settings > Apps`), using external
graphical configuration tools such as [Flatseal](https://flathub.org/en/apps/com.github.tchx84.Flatseal)
or [Warehouse](https://flathub.org/en/apps/io.github.flattool.Warehouse), or with the
[`flatpak override`](https://docs.flatpak.org/en/latest/flatpak-command-reference.html#flatpak-override)
command in a terminal.

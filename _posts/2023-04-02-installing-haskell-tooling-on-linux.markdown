---
layout: post
title:  'Installing Haskell tooling on Linux'
date:   2023-04-02 19:40:25 -0400
categories: haskell tools guide functional programming
---

As one of the most popular and well known functional programming languages, Haskell is a truly interesting language.
I'll be explaining how you can go about installing GHCup, HLS (Haskell Language Server,) and cabal on Linux.

# Installing GHCup
According to the [Haskell site on GHCup](https://www.haskell.org/ghcup/), most systems (Linux, macOS, FreeBSD) can simply use this following command to install GHCup.
{% highlight bash %}
$ curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh
{% endhighlight %}
Throughout the installation, it will ask you if you would like to install HLS, and if you would like to enable better integration with the Haskell Stack tool, and I would recommend simply saying no during this phase of the installation, as we will be installing specific versions after.
On most distributions, the installation should go fine instantly, but on certain distros like Void Linux, you will need to install some libraries to get it to install fully.
On voidlinux, you can simply install the 'ncurses-libtinfo-{devel,libs}' packages to finish.
{% highlight bash %}
$ sudo xbps-install ncurses-libtinfo-{devel,libs}
{% endhighlight %}

# Using GHCup
Now that we successfully have GHCup installed, we can get on with installing HLS and cabal!
We will be covering the installation using GHCup, though on some distributions they will offer a native package for cabal & HLS. I would recommend still sticking with GHCup for the installation, as it is the only way that is officially supported.
{% highlight bash %}
$ ghcup tui
{% endhighlight %}

GHCup should display something similar to the following:
![interface](/assets/images/intro/fol.png)

You can simply navigate to the 'HLS' and 'cabal' options on each recommended setting and hit 'i' for install, then after the installations finish, you can hit 's' to set them.


Now you should be able to execute 'cabal' and use the language server with your editors.

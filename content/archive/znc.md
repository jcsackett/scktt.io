+++
date = 2011-02-21T22:06:00.000Z
title = "ZNC"
draft = false
+++
### The Situation

Staying in touch is a requirement for everyone working on
[Launchpad](http://launchpad.net "Launchpad"), much as it is for all of
Canonical.

In addition to using a ton of email, voice chat tools like
[mumble](http://mumble.sourceforge.net/ "Mumble") and
[skype](http://skype.com "Skype"), our biggest communication medium is
IRC. While any other tool is a “use when you need it” sort of thing, the
expectation is that you will always be on IRC.

### The Problem

I use two computers in my work day—my mac for a lot of coding and some
design work, as well as project tracking, and my [Darter
Ultra](http://knowledge76.com/index.php/Daru2) for serious work and ui
testing. Staying on IRC on both computers can be a hassle. Either I’m
using different nicks on each one and making my colleagues figure out
which one is the “real” me at any given moment, or I’m going through a
sign-off, sign-on dance as I swith between machines. Add in that I have
an IRC client on my phone and my iPad that I sometimes use (if I’m
moving away from the computer or commuting for a bit, but want to stay
in touch) and I have serious complications and hassles for me, my
coworkers, or both.

### The Solution

There is a *fantastic* tool called
[ZNC](http://en.znc.in/wiki/ZNC "ZNC") which steps into save the day.
It’s an IRC bouncer, which relays connections from one computer to
another. I set it up on my server, and have it login to all of my IRC
networks. Then, I connect to it from all of my IRC clients.

The end result is that each client is actually just using the same
connection; I can be on IRC from all of my devices, using the same nick,
and sharing the same chat history, without going through any sort of odd
sequence of signing off and signing on.

There are some additional perks too. ZNC lets me always be on IRC, so I
don’t miss any mentions of my nick or conversations I need to know
about. It can log all conversations on the server, as well as
transmitting some set number of lines of history to any client when you
sign on. There’s also a host of plugins, like a
[webadmin](http://en.znc.in/wiki/Webadmin) for your ZNC configuration or
a [notifo plugin](http://en.znc.in/wiki/Notifo) to send your highlights
to your mobile device.

It’s easy to setup on ubuntu servers; ”’sudo aptitude install znc”’ and
then some simple configuration. If you use IRC a lot, especially from
several devices, give it a try!

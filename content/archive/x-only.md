+++
date = 2010-11-18T02:18:00.000Z
title = "X Only"
draft = false
+++
[One Thing Well](http://onethingwell.org/post/1432068153/x-only) had a
really useful post not too long ago showing how to run an X application
without firing up a full window manager.

In my work, I use a number of servers (running as VMs). These have
firefox installed, because it’s a dependency for the launchpad windmill
tests. But, because they’re servers, they don’t have any windowing
environment, and I’d really rather not install one. This x only trick is
so useful for me, that I scripted up a little version of it that I can
pass an application and tty \# to it without having to think about the
xinit arguments.

The gist for it is below:

It is, obviously, trivially simple. But it is *so* handy. Thanks to One
Thing Well for sharing this.

+++
date = 2009-07-21T01:13:00.000Z
title = "Introducing Weaver"
draft = false
+++
### The Problem

I work in Django, both professionally and in side projects. This leads
to an ever growing number of sites to do deployment and updates on.
Deployment is repetitive and irritating, even when you can just copy and
paste config files around and do some local edits. Stuff always breaks,
and take way more time than you thought you would.

### The Solution

Automated deployments. For Django, right now, that means
[Fabric](http://www.nongnu.org/fab/), which is a great utility. Simply
write a fabfile, maybe with a few helper scripts here and there, and you
have a utility to deploy to server after server, and update whenever you
need to.

### The Problem With The Solution

You still have to write the fabfile conf files and scripts (if any). And
while there’s less tweaking to be done once you’ve written it all, it’s
still a pain. Again, you can do the copy and paste thing, but it’s still
error prone, and if you’re me, still annoying.

### Enter Weaver

[Weaver](http://github.com/jaycee/weaver/tree/master) makes fabric.
Which is a pithy way of saying that weaver is a simple utility to create
a fabfile, conf files, and some helper scripts to get everything laid
out nicely.

### Problems with the Solution to the Problem with the…yeah

Weaver is really suited to my style of deployments. As such, it makes a
whole host of assumptions about the nature of your deployment. These are
outlined in the README.

### Other Stuff

It’s released under BSD.

I hope you find some use for it. Comments are welcome here. Issues are
welcome at github.

+++
date = 2010-03-30T22:25:00.000Z
title = "Better svn modification tracking"
draft = false
+++
We use svn at work (we’re looking at hg or git, but that’s a different
discussion) and we have projects with huge external lists. That means
the output of a generic **svn st** command can be incredibly difficult
to parse.

I’ve been using **—ignore-externals** and piping through grep often
enough that I finally slapped it into a shell script on my path. It’s
been incredibly useful for me; perhaps it will be for you as well.

+++
date = 2012-03-16T21:36:00.000Z
title = "Colocation with Bazaar (the glorious fix!)"
draft = false
+++
Last I [blogged about
bzr](http://blog.humanmade.org/post/19018238488/colocation-with-bazaar),
I complained about screwing up my use of `bzr lp-propose`. As suspected,
this was entirely my fault, and there is one line to fix it.

In my locations.conf file I added the following.

    [/home/jc/Code/launchpad/devel/.bzr/branches/devel]
    public_branch = bzr+ssh://bazaar.launchpad.net/~launchpad-pqm/launchpad/devel

The public branch for your trunk is pretty important, as it turns out.
So, bzr becomes a little bit closer for me, and if you’re following
along and using it, hopefully for you too.

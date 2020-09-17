+++
date = 2009-02-18T11:13:00.000Z
title = "A New Blogging System"
draft = false
+++
Based on posts like
[this](http://inessential.com/2009/01/30/new_publishing_system_tour_of_my_head)
and system like
[this](http://github.com/al3x/simple-scala-blog/tree/master) I’ve
started playing with my own ideas for a new system.

Totally static pages appeal to me—I get comments via Disqus, so I don’t
run that on my server. Most other dynamic elements one needs for a blog
can be outsourced. Having my entire blog in version control appeals to
me.

I’m thinking a system that pushes plaintext files in markdown through
[Jinja](http://jinja.pocoo.org/2/) and resyncs a main dashboard showing
most recent posts. All rendered pages kept in a filetree that shows
their post-time and title.

Properly tumbly stuff will stay here, of course. By which I mean, in
tumblr. It’s conceivable that the subdomain for tumbling will be moved
to something like tumble.humanmade.org and this site will be a proper
publishing point.

More as this develops.

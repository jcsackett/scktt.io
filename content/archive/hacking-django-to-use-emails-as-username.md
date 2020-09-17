+++
date = 2009-08-06T22:58:00.000Z
title = "Hacking Django to use Emails as Username"
draft = false
+++
There’s a fair number of times you want to use email as a login when
you’re designing a site as opposed to say, a username.

In django, you can get partway there by setting up a custom auth
backend, say as shown
[here](http://www.djangosnippets.org/snippets/74/).

But that only goes so far.

The admin app (blessed though it may be) has its own ideas about
usernames and authentication.

To deal with that, your best bet is subclassing the admin stuff and
reregistering, comme ca:

Django admin: The handiest thing to beat up ever.

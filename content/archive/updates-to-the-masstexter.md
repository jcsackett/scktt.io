+++
date = 2010-03-18T02:41:00.000Z
title = "Updates to the MassTexter"
draft = false
+++
I just pushed a few changes to
[masstext](http://github.com/jaycee/masstext/) on github.

As I said, I was working on setting up some basic call list style groups
and moderation. A few updates have laid some groundwork for that, and
now there’s full support for simple groups:

-   A user’s phone number can belong to one, and only one call list.
-   A call list can be marked as moderated or unmoderated from the web
    interface (a django admin site).
-   On moderated lists, a phone number must be listed as one that
    can\_send in order to broadcast to the list.
-   On unmoderated lists, anyone can send.
-   New lists default to unmoderated; new phone numbers default to
    having send privileges.

If anyone has successfully used the application themselves, I would love
to hear about it!

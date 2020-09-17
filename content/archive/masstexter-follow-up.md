+++
date = 2010-02-26T16:34:00.000Z
title = "MassTexter Follow Up"
draft = false
+++
So, it’s the end of the week, and I thought I would write some follow up
information on the masstexter.

I got the masstexter up and working Thursday night; we used it for all
of PyCon. With ten people using it we had a really high response
rate—people generally got the message sent to them within seconds of
someone sending a message out. I left the code sending the message to
everyone in the list—including the sender—so as to maintain some sort of
confirmation that the message was sent. But at \$0.03 a text, I removed
that feature. With the feature, pretty heavy usage of the texter ran a
cost in three days of about \$60. That’s about 180 uses with ten users.
Without the confirmation message, that would go up to about 200 uses.

The application turned out to very useful—we had planned on using a
chatroom on our company VPN for communication, but given some pretty
prevalent wifi issues we ended up falling back on the masstexter more
than I had planned.

Towards the end of the con, I threw in another modification, though we
never had too much need for it; if someone not in the masstext database
sends a message, it doesn’t pass that message on. I realized that if
someone got ahold of the twilio number, they could easily spam all of us
without any penalties, driving up the cost of the application and
irritating everyone. That change was pushed up to
[github](http://github.com/jaycee/masstext).

I’m looking into some other features as well; chief among these is some
sort of grouping feature, and usage of an asterix server to cut down on
the costs of sending messages out.

I’m also considering what license to push this out under; something
better than the informal “it’s on github, feel free to play.” If anyone
has recommendations, let me know—otherwise I’ll probably default to the
BSD License or similar.

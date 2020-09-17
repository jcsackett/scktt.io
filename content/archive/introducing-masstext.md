+++
date = 2010-02-21T06:50:00.000Z
title = "Introducing MassText"
draft = false
+++
This past weekend, I was at PyCon. My entire department went, which led
to some communication difficulties. While we all had each other’s mobile
numbers, text messages and phone calls were requiring a phone tree
system, which was both lossy—not everyone got the messages—and really
inefficient.

Not to mention irritating.

### Programming to the Rescue

Fortunately, [Twilio](http://twilio.com) recently released an SMS
service, which makes programming SMS powered web apps really simple.
With a little django power, I was able to put together a simple webapp
that can accept an SMS and send it on to a number of other people.

### MassText

Unoriginally, I’ve entitled the project MassText. It’s a surprisingly
simple application—only one model, only one view (plus a little love
from **contrib.admin** and **contrib.auth**). The model stores a phone
number and who owns said number; the view handles the send and receive
via Twilio.

The basic process works like this:

-   An SMS is sent to a Twilio number.
-   Twilio sends a **POST** to the masstext view.
-   The masstext view:
-   -   pulls the other users in the list

-   -   creates a Twilio XML response containing the original sms
        message for each user.

-   -   Sends the response to Twilio

-   Twilio sends the defined SMS messages to all users.

Like I said, simple.

### I Wanna Play Too!

I’ve put the code up on [github](http://github.com/jaycee/masstext).
I’ll be adding official licensing and working on better features in
time. Feel free to take a look and set it up yourself.

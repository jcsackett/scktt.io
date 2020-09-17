+++
date = 2008-09-02T20:39:00.000Z
title = "Text Clustering and Latent Semantic Analysis"
draft = false
+++
![]()

Work involves a lot of natural language processing and information
retrieval. Or at least, it’s *supposed to*. With that in mind, I thought
it would be worthwhile to do a bit of research/relearning on a major NLP
technique, Latent Semantic Analysis (LSA).

The basic idea of LSA is term clustering as a means of comparing
documents. It’s pretty involved mathematics wise, and I haven’t yet
grasped all the details. But, at its simplest it’s just a form of
term/document clustering.

It starts with a bunch of documents, which are stoplisted and stemmed so
that you’re left with the most important stuff. Basically “hate” and
“hating” become the same token and things like “the” and “is” are
removed. A matrix for the documents and their terms is then created,
e.g. :\
\
D1 “I hate analysis.”\
D2 “I hate, HATE cheese burgers.”

I     hate     analysis     cheese     burgers

D1      1    1          1              0             0

D2      1    2          0              1             1

![]()

![]()

![]()

From there you can start clustering data. A high occurrence of certain
words indicates a likely semantic meaning.

And then you run up into the linear algebra. Since I barely remember
what an eigenvector is, I’m still working on that part. I’ll continue
blathering on this when and if I’ve got that sorted.

(**Argh:** that table up there is sort of unreadable, as tumblr has no
real support for, well, tables. Sorry about that. If you’ve got a
solution, post in the comments.)

+++
date = 2010-01-26T02:07:00.000Z
title = "Writing Like A Programmer"
draft = false
+++
I fancy myself a writer. Not, mind you, a *good* one. Just a passable
one.

I am, however, definitively a programmer. This means that I like things
like version control, scriptable or programmable tools, and open, easily
interchangeable formats.

Currently, when I write things I write them in RTF or in ASCII with
Markdown. I *really* like Markdown. I used to like RTF, until I realized
that it has no really standard implementation. So I have resolved to
move my writing away from RTF and into Markdown only.

So, ideally, here’s my writing setup:

-   Any writing project is a git repository.
-   All source files for the project are written in Markdown
-   When a project is finished, an HTML version is produced using the
    python implementation of Markdown
-   Additionally, when a project is finished, a PDF version is created
    with wkhtml2pdf
-   Optionally, if I want to get designery, output files include some
    nice CSS, injected in either through a hack or some sort of nice
    templating tool (Jinja, anyone?).

It seems like a nice idea. Of course, the problem with it is that I have
a bunch of stuff **not** produced in this fashion, and I need to convert
it (mostly because I’m slightly OCD about having all my stuff in a
similar state, but that is neither here nor there). Aaron Swartz has a
nice tool called html2text, which works *reasonably* well as part of an
RTF to HTML to Markdown conversion flow. The only problem now is that
the Markdown produced doesn’t return to an entirely accurate final
format.

I’ll continue on here about my experiments in this vein. In the
meantime, other writers reading this: what is your setup, ideal or
otherwise?

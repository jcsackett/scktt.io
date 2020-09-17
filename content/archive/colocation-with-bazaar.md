+++
date = 2012-03-09T21:40:00.000Z
title = "Colocation with Bazaar"
draft = false
+++
(***UPDATE GUYS***: I fixed the problem outlined in this post. Please go
ahead and finish reading it, but then [go
here](http://blog.humanmade.org/post/19410890644/colocation-with-bazaar-the-glorious-fix)
to read about what was missing.)

I use Bazaar (bzr) for work. On just about everything else, I use git. I
like both—for very different reasons—and basically just use whichver one
the code I’m working on is primarily available. So work, bzr, and side
projects (which began on github), git.

The only real oddity this creates for me has to do with branching. Git
colocates its branches by default. You have one working directory, and
the contents of that directory may change as you switch between
branches. All the history and metadata about the branch is hidden away
in the .git directory.

Bazaar puts each branch in its own directory—switching branches means
changing the directory you’re in, rather than changing the contents of
your current directory.^[1](#fn:p19018238488-1)^ This is actually a
really good system for the novice DVCS user. New branches are new
directories, what could be simpler? But if you’re used to branching in
git (or mercurial for that matter) it’s a little weird.

To address this, there’s a plugin named bzr-colo. Bzr colo lets you work
with branches the way you would with other DVCSes. Since for work I use
a shared repository with a ton of little branches, I thought setting up
a single directory with colocated branches for launchpad work would be
cool.

### The experiment

Setting things up seemed pretty easy.

    bzr branch lp:launchpad ./devel
    cd devel
    bzr colo-ify

I also added some stuff in my `locations.conf` so `bzr push` and the
like worked properly.

    [/home/jc/Code/launchpad/devel/.bzr/branches]
    public_branch = bzr+ssh://bazaar.launchpad.net/~jcsackett/launchpad
    public_branch:policy = appendpath

    push_location = lp:~jcsackett/launchpad
    push_location:policy = appendpath

    submit_branch = /home/jc/Code/launchpad/devel/.bzr/branches/devel/
    submit_to = merge@code.launchpad.net

This sort of echoes the setup of our shared repo setup as established by
our [recommended
setup](http://bazaar.launchpad.net/~launchpad-pqm/launchpad/devel/view/head:/utilities/rocketfuel-setup).
I had to rename the default branch in my colocated directory as well,
since bzr-colo wants to call it trunk.

With this setup, I started a new branch with `bzr colo-branch` and got
to work.

### The results

For the most part, things worked as I expected. I was able to `bzr pull`
into devel, and bzr merge from it into my current branch. `bzr push`
worked as expected too. Everything seemed groovy.

Then I hit my one snag.

I attempted to submit my branch for code review using `bzr lp-propose`.
Sadly, the branch I was evidently proposing against was
lp:\~jcsackett/launchpad/devel, rather than lp:launchpad.

I’m pretty sure this is a problem in my locations.conf; I will be the
first to admit I don’t know entirely what all of those settings mean, or
how they are used. I hope to get that problem sorted and go back to
using this setup soon, and will post a follow up when I do.

<div class="footnotes">

------------------------------------------------------------------------

1.  <div id="fn:p19018238488-1">

    </div>

    For the most part, that is. Bazaar has *lots* of options, and with
    lightweight checkouts and shared repositories you can end up with a
    single working directory you switch in, but the branches are still
    all separate ones at the same layer in the file tree. It’s handy,
    but gets confusing. [↩](#fnref:p19018238488-1)

</div>

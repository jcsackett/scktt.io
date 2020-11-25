---
title: "Deploying With Gitea"
date: 2020-11-24T21:15:05-05:00
subtitle: "Blogging like it's 2010, baby!"
---

As of last week this blog gets deployed via a private gitea repository. I
know, I know, not that impressive, but I'm going to write it up anyway, and if
you don't care you can smile and nod and close the tab.

[Gitea][gitea] is great git hosting webapp (and git server) that is really
simple to [set up][install-docs]. 

I've been meaning for some time to set up my own git server for personal
projects in lieu of hosting *everything* on github, and the work I've been
doing to update this site seemed like a good time to do that. So after quickly
setting it up (just follow the docs) I started pushing this site's repo to it
when I realized I had the opportunity to do something clever (that other folks
have been doing since static site generators and git were a thing).

I have always updated this site via rsync. This is fine, but it means that
deploys of the site may not have been committed. It would be much better to
use the git repo itself as the means of deployment.

Gitea has great support for git hooks. So following a few examples I've found
for using githooks for hugo, I set one up on my server.

I'm using the snapped version of hugo locally, so I installed the snap on the
server this runs on. Snaps are isolated from doing things like writing all
over the filesystem, so my hook script ended up a bit of a hack, as you can
see:

```bash
#!/bin/bash

GIT_REPO=$PWD
WORKING_REPO=$HOME/scktt.io-tmp
BUILD_DIR=$HOME/scktt.io-build
PUBLIC_WWW=/var/www/scktt.io
BACKUP_WWW=$HOME/scktt.io-bak
HUGO=/snap/bin/hugo

set -e

revert_on_error() {
  "echo 'A problem occurred.  Reverting to backup.'
  rsync -aqz --del $BACKUP_WWW/ $PUBLIC_WWW
  rm -rf $WORKING_DIRECTORY"
}

rm -rf $WORKING_REPO $BUILD_DIR
rsync -aqz $PUBLIC_WWW/ $BACKUP_WWW
trap revert_on_error EXIT

git clone $GIT_REPO $WORKING_REPO
# hugo snap can't write outside of $HOME; use $BUILD_DIR
$HUGO -s $WORKING_REPO -d $BUILD_DIR
rm -rf $WORKING_REPO

rm -rf $PUBLIC_WWW/*
rsync -aqz $BUILD_DIR/ $PUBLIC_WWW
rm -rf $BUILD_DIR $BACKUP_WWW
trap - EXIT
```

The `trap` usage is pure cargo-culting; I need to actually read how it works,
but the script does seem to handle failures pretty well (my site has never
just been deleted). If I were more daring, I think I could probably also run
hugo directly out of the main git repo and skip a step.

But, crucially, it works. If you've been looking at setting up something
similar and give this a try, I'd love to hear about it. And if you think
there's something wrong here or a way it could work better, I'd also love to
hear from you.

[gitea]: https://gitea.io
[install-docs]: https://docs.gitea.io/en-us/install-from-binary/

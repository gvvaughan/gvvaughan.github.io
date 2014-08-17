---
layout: post
title: Git Upstream Repo Tracking
---

Between forking [Jekyll Now](https://github.com/barryclark/jekyll-now) to serve this site, and beginning this first post, the upstream repository gained several new commits.  With a bit of digging, I reminded myself of the  `git` commands necessary to merge those upstream changes back into my forked repository (of course, I needed to clone the forked repo to my local computer first!):

{% highlight sh %}
# Track and fetch an upstream branch locally:

$ git remote add upstream git://github.com/barryclark/jekyll-now.git
$ git fetch upstream

# Merge into local master:

$ git checkout master
$ git merge upstream/master

# And push the changes back to github:

$ git push
{% endhighlight %}

In this case, I had to resolve some small conflicts with edits I'd made in the fork, but otherwise everything is now back in sync again :-)

In future, now that I already have the `upstream` tracking branch, I can easily fetch any other changes and merge those in too:

{% highlight sh %}
# Update and merge back to local master:

$ git fetch upstream
$ git checkout master
$ git merge upstream/master

# And push the changes back to github:

$ git push
{% endhighlight %}

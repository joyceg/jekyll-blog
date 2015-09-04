---
author: geojoyce
comments: true
date: 2015-06-05 11:15:04+00:00
layout: post
slug: write-brokebroken-pipe-issue-solved
title: WRITE BROKE,BROKEN PIPE ISSUE [SOLVED]
wordpress_id: 113
categories:
- GIT
- Linux
---

Hey all,
Recently I was cloning a git repository(mediawiki core).As you all know it takes a lot of time as there is a large amount of data and moreover my campus wifi is not in a good pace.I waited a long time(around 4 hours),the cloning reached 99% and I was feelling very much excited.Suddenly something like this popped out:
[![broken_pipe](https://geojoyce.files.wordpress.com/2015/06/broken_pipe.png?w=300&h=37)](https://geojoyce.files.wordpress.com/2015/06/broken_pipe.png)

I repeated the same process three times,but faced the same error all the times.(I think many who have cloned large repositories have faced the same).This is mainly due to network problem.
So,googled a lot and got help from some of my friends(special thanks Dhanvi ;))

It was fixed by trying the shallow clone,i.e
Here we are not cloning the git repo at a stretch,the process is divided
Step 1:
`git clone --depth=1 git_repository`

Step2:
Enter the cloned repo.
Deepen the clone using:
`git fetch --depth=N git_repository`
Note:N should be substituted with any positive value

Step 3:
To download rest of the revisions;

`git fetch --unshallow git_repository`

Have fun ;)

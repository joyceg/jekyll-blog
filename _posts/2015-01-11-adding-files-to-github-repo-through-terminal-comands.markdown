---
author: geojoyce
comments: true
date: 2015-01-11 15:24:39+00:00
layout: post
slug: adding-files-to-github-repo-through-terminal-comands
title: Adding files to GITHUB REPO through terminal comands
wordpress_id: 75
categories:
- GIT
- Open source
---

GO to your GIT-HUB and create a new repository.

Now open a new terminal(Alt+Ctl+T),

Now move to the directory from which you need to add file to the GIT repository created,
Initialize the directory as a git repository by the command
`git init`
Now moving on to adding the files,
If you want to enter all the files inside that directory,enter
`git add .`
If you want to add only a specific file under that repository ,enter
`git add file_name`

Now you need to make a commit mesage,enter
`git commit -m "commit message"`

Now add the url of the repository created in github,
For doing that copy the ssh address of the repo given in the bottom-right side of the github repository and enter
`git remote add origin url`

Enter the following to verify the url
`git remote -v`

Now to push the file to the github repo,enter
`git push origin master`

If the above code doesn't work,enter following
`git pull origin master`
`git push origin master`

Thus,the file is added to your git-hub repo. :)

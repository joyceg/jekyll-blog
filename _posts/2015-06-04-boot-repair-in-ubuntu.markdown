---
author: geojoyce
comments: true
date: 2015-06-04 03:40:15+00:00
layout: post
slug: boot-repair-in-ubuntu
title: Boot Repair in ubuntu
wordpress_id: 97
categories:
- Dual boot
- Linux
---

Boot repair is something which is really necessary if you are having multiple Operating systems in your system.This post will help you to do boot repair in ubuntu.

A breif introduction which resulted me to do boot repair recently:
Last night,I was trying to fix some driver errors and installed some new softwares into my windows machine.I downloaded all the drivers and necessary softwares from HP website(am having a HP Laptop).All the driver issues were fixed comfortably and I was really happy that after some work I have set up the windows - ubuntu dual boot .

But,unfortunately,when I restarted my system,I could no longer see my grub.I was directly booted into my windows os.I never expected it because I  spend a long time working on installing many necessary softwares in ubuntu.But,when I went to my disk partition,I saw the ubuntu partition alive.Moreover,I also thought of reinstalling ubuntu and I inserted a live CD.But,I saw a message like erase your ubuntu 14.04 and install new ubuntu which strengthened me.I understood that some softwares  or drivers I have installed screwed me.

I went into windows and uninstalled some of the softwares.Now,I could see my ubuntu OS in the BOOT MENU OPTIONS.But,since I had to do some extra steps to get into my ubuntu every time ,I thought of doing a boot repair.Some of the commands I got from the Internet didn't work for me.I had to do more search .So,here goes BOOT REPAIR:

Boot into your ubuntu machine and get connected to the internet.Open a terminal and enter
Step1:`sudo add-apt-repository ppa:yannubuntu/boot-repair`
If the above command was working successfully,go ahead with the next step,
If you got something like this:
[![ppa_error](https://geojoyce.files.wordpress.com/2015/06/ppa_error.png?w=300)](https://geojoyce.files.wordpress.com/2015/06/ppa_error.png)

Dont worry, go to [Launchpad ](https://launchpad.net/~yannubuntu/+archive/ubuntu/boot-repair) and click on technical details about this ppa and select you ubuntu version.Select you ubuntu and you will see 2 lines of instruction in the rectangular box below.
You need to manually add the ppa.
Enter in the terminal:
`sudo gedit /etc/apt/sources.list`
You will get a text document with PPA's.Go to the bottom and paste the 2 lines you have seen in the rectangular box.
Now,
`Sudo apt-get update`
So,now you are done with adding the ppa.

Step2:`sudo apt-get update`(no need to do again,if you have done while adding ppa)

Step3:`sudo apt-get install -y boot-repair && boot-repair`

You will see:
[![boot_repair](https://geojoyce.files.wordpress.com/2015/06/boot_repair.png?w=300)](https://geojoyce.files.wordpress.com/2015/06/boot_repair.png)

Selected recommended repair.
Once it is finished.Restart into you system.You will get something like:
[![grub](https://geojoyce.files.wordpress.com/2015/06/grub.png?w=300)](https://geojoyce.files.wordpress.com/2015/06/grub.png)

I hope this helped you.Have fun ;)

---
author: geojoyce
comments: true
date: 2014-11-14 15:13:17+00:00
layout: post
slug: error-mounting-disks
title: Error mounting Filesystem
wordpress_id: 59
categories:
- Linux
---

[caption id="attachment_60" align="alignnone" width="300"][![A usual scene while using dualboots](https://geojoyce.files.wordpress.com/2014/11/screenshot-from-2014-11-14-201710.png?w=300)](https://geojoyce.files.wordpress.com/2014/11/screenshot-from-2014-11-14-201710.png) A usual problem in Dual-Boots[/caption]

This is a common error you can see in ubuntu if you are using multiple Operating systems in your system.I too had the same problem.I found that this error appears due to some shutdown mistakes you commit in Windows.I could solve this sytem by adding some codes to the fstab file.If you ever face this problem of mounting devices,you can follow this.

Open a terminal(Alt+Ctrl+T),

1.Enter **sudo blkid**
This is to get the to get the UUID (Universally Unique Identifier) of the partition you want to mount.
If you have 3 Windows partitons,you will see 3 UUIDs.Each partiton is having a unique ID.

2.Now you need to open fstab file in your system to add the UUIDS of the partitions that needed to be mounted.

Enter** gksu gedit /etc/fstab**

If you don't have gksu installed in your system please do the following steps:

sudo **apt-get update**

sudo **apt-get install gksu**

now run,
**gksu gedit /etc/fstab**

3.Now add the following line at the bottom of the file you have opened

**UUID=1234567890123456 /media/ntfs ntfs rw,nosuid,nodev,noatime,allow_other 0 0**

Replace the "1234567890123456" with the UUID you have got in the first step.
If you have done more than 1 partition make sure to add the UUIDs of all the partitions in the similar manner.

Now click save and close the fstab.
Restart the system and check whether the partition is mounted.

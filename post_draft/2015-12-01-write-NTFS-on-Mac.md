---
layout: post
title: "Write to NTFS Drives on Mac OS system"
date: 2015-12-01
---


An annoying problem using Mac is that the OS X system on Mac does not support NTFS drives. When I try to write a file to the external disk in NTFS format, the OS X system refuses to do so and throws out an error that the disk is read only. One simple solution to install [NTFS for Mac](http://www.paragon-software.com/home/ntfs-mac/). However, it is not free. Therefore, I try to find other solutions and I happed to find [this one](http://computers.tutsplus.com/tutorials/quick-tip-how-to-write-to-ntfs-drives-in-os-x-mavericks--cms-21434). I tried it on my Mac and it worked!


1. First, edit the /etc/fstab file by `sudo nano /etc/fstab`. On my Mac, there is one file called fstab.hd but this is not the one we want to edit. 

2. Then, add  `LABEL=drivename none ntfs rw,auto,nobrowse` to the file. Replace the `drivename` with the actual drive name. Save the file.

3. Unmount and unplug the external dive and re-plug it. You will not be able to see the external drive on Finder's Devices menu. Use `Finder's menubar` -> `Go` -> `Go to Folder` -> Type '/volumes' as the path. You will see the external drive. You can drag the external drive to the sidebar. Also, you can use `ln -s` to link the external drive to whereever you want. 






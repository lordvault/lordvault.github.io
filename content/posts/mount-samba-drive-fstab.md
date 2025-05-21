---
title: "Mount Samba Drive Fstab"
date: 2025-05-21T13:26:42-05:00
draft: true
---

## How to mount a Network Drive with fstab

In my current "home lab" i try to have a centralized data point to generate backups and make more easy the restore of an application. For my case i have a NAS with a SAMBA shared drive, this drive its not hard to create, you can use some old drives and use TrueNas to manage your data, user, folders, etc. 

So my to mount a samba shared file i use the following commands:


```
#create the folder to mount on your system.
mkdir /mnt/z
```
Edit the fstab config, i use nano, but you can use any other one.
```
#sudo -s 
nano /etc/fstab 
``` 

``` 
#Copy this line at the end of file
//192.168.0.XXX/<yourfoldershared> /mnt/z cifs username=<your-user>,password=<yourpass>,vers=3.0,auto,x-systemd.automount,uid=1000,gid=1000
```
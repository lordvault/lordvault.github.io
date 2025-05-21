---
title: "Backup Docker Volume"
date: 2025-05-21T15:42:38-05:00
draft: false
---

## Backup a docker volume

In search to backup all my media services, i found this docker [Loomchild Volume Backup](https://hub.docker.com/r/loomchild/volume-backup). This image allows to mount any docker volume and generates as output the compressed file in tar. I ussually use this docker in combination with the crontab linux feature, schedulling the backups and doing this proccess regularly to save the information. 


Command: 
```
docker run -v <abosule_volume_name>:/volume --rm --log-driver none loomchild/volume-backup backup - > <output-file-path->.bck.tar.bz2
```
---
date: '2010-03-31T11:30:57-05:00'
tags: []
title: Formateé mi disco principal en ntfs (obviamente por error)
tumblr_url: https://blog.millaguie.net/post/486332427/formate%C3%A9-mi-disco-principal-en-ntfs-obviamente
url: /2010/03/31/formateé-mi-disco-principal-en-ntfs-obviamente/
---

Y gracias a que tenía dos discos particionados igual y varios raid sobre particiones lo único que he tenido que hacer es:

> dd if=/dev/sdb of=/dev/sda bs=512 count=1

> mount /dev/md0 /mnt

> cd /mnt

> chroot .

> grub-install /dev/sda

y reiniciar…

se me ha recuperado hasta el raid0… a los raid1 he podido acceder en todo momento…

así que:

¡vivan los sistemas raid!

¡viva ext4!
---
date: '2014-01-09T19:35:00-06:00'
tags:
  - backuppc
  - mover de servidor
title: Como mover copias de seguridad de backuppc de un servidor a otro
tumblr_url: https://blog.millaguie.net/post/72783186323/como-mover-copias-de-seguridad-de-backuppc-de-un
url: /2014/01/09/como-mover-copias-de-seguridad-de-backuppc-de-un/
---

Básicamente:

> su - backuppc
> 
> cd /var/lib/backuppc
> 
> rsync&nbsp; -e “ssh -c arcfour"&nbsp; -avP –exclude pc/\* trash/\* ./ newserver.example.com:/var/lib/backuppc/
> 
> /usr/share/backuppc/bin/BackupPC\_tarPCCopy /var/lib/backuppc/pc |ssh -c arcfour&nbsp; root@newserver.example.com "cd /var/lib/backuppc/&nbsp;; tar xvPf -”

El rsync, puede tardar algunaos horas días…
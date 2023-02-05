---
date: '2011-09-02T11:24:55-05:00'
tags:
  - codificación no válida
  - ubuntu
  - utf8
  - convmv
title: Solucionar problemas de codificación en los nombres de los archivos
tumblr_url: https://blog.millaguie.net/post/9700916695/solucionar-problemas-de-codificaci%C3%B3n-en-los
url: /2011/09/02/solucionar-problemas-de-codificación-en-los/
---

Muchas veces te habrá pasado que al descomprimir un RAR o al bajarte algún torrent con linux los ficheros tienen nombres con la codificación no válida o directamente caracteres chungos que luego muchas veces no te deja trabajar con ellos.&nbsp;

Gracias a que el monesvol es todo poderoso tenemos un ayudante que nos soluciona esta papeleta, se &nbsp;trata deconvmv y se ejecuta así:

> &nbsp;&nbsp;convmv &nbsp;-r -f iso8859-1 -t utf8 directorio\_chungo

seguramente luego os pida meter una opción más para asegurarse de que no está metiendo la pata al hacer lo que le pides ;)
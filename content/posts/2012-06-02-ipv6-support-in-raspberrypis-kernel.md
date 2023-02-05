---
date: '2012-06-02T13:40:00-05:00'
tags:
  - Raspberry Pi
  - IPv6
title: IPv6 Support in RaspberryPi's kernel
tumblr_url: https://blog.millaguie.net/post/24255339881/ipv6-support-in-raspberrypis-kernel
url: /2012/06/02/ipv6-support-in-raspberrypis-kernel/
---

Yesterday arrived my Raspberry Pi, I’m thinking about making some appliances just for fun. I’ll prepare some ready to burn SD images with the appliances.

The first one is a IPv6 tunneling router. Some minutes after you plug this RaspberryPi in your network you’ll have IPv6 conectivity in your network, just plug and play ;)

I’ll be using IPv6 autoconfiguration and tunneling. So, it’s not really complicated. &nbsp;

The first problem ahead is Raspberry Pi Debian’s kernel doesn’t have IPv6 sopport. I had to compile a new one.

If you need IPv6 support in your raspberry you can download it from:&nbsp;[http://www.millaguie.net/misc/kernel\_raspberrypi\_ipv6.tar.gz](http://www.millaguie.net/misc/kernel_raspberrypi_ipv6.tar.gz "IPv6 Support for Raspberry Pi") , you have to decompress it on your root filesystem, but please, make backups before.
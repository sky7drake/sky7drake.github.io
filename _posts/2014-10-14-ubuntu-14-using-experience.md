---
layout: post
title: "ubuntu 14 using experience"
description: "some using experiences of ubuntu 14.04 trusty"
category: [中文, exp] 
tags: [exp, ubuntu]
---
{% include JB/setup %}


## emacs
sudo:

> (require 'tramp) C-c C-f /sudo::/path/to/file 

## edit hosts
[最新 host file](https://raw.githubusercontent.com/zxdrive/imouto.host/master/imouto.host.txt);
[github地址](https://github.com/zxdrive/imouto.host)

	gedit /etc/hosts
	# restart network
	/etc/init.d/networking restart

## ubuntu 14.04 trusty 记录屏幕亮度 
[ref](http://ubuntuguide.net/how-to-save-screen-brightness-settings-in-ubuntu-12-04-laptop)

	gedit /etc/rc.local
	# append the following line before "exit"
	echo #brightness# > /sys/class/backlight/acpi_video0/brightness




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

```sh
gedit /etc/hosts
# restart network
/etc/init.d/networking restart
```

## adjust screen brightness 记录屏幕亮度
 
[ref](http://ubuntuguide.net/how-to-save-screen-brightness-settings-in-ubuntu-12-04-laptop)

```sh
gedit /etc/rc.local
# append the following line before "exit"
echo #brightness# > /sys/class/backlight/acpi_video0/brightness
```

## add name server

http://unix.stackexchange.com/questions/128220/how-do-i-set-my-dns-on-ubuntu-14-04

Ubuntu 14.04 trusty uses **resolvconf** to generate **/etc/resolv.conf** file, therefore we need to modify the the config of resolvconf. Prepend lines as follows and let resolvconf regenerate resolv.conf

```sh
sudo bash -c "echo \"nameserver 8.8.8.8\" >> /etc/resolvconf/resolv.conf.d/head"
sudo bash -c "echo \"nameserver 8.8.4.4\" >> /etc/resolvconf/resolv.conf.d/head"
sudo resolvconf -u
```


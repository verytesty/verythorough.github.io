---
layout: post
permalink: ''
published: false
title: Manual DNS Fun
date: 2017-01-31T03:25:43.372Z
---

Today I had to set up the DNS MX records for OpenSMC, changing them to point to google.  I've managed DNS many times before via domain registrar consoles, but the registration for opensmc.org was on our server admin's personal account, and he preferred to roll his own DNS anyway.  So, now I got to figure out how to manually change a zone record.

Notes:
- These [two](http://www.tldp.org/LDP/lame/LAME/linux-admin-made-easy/domain-name-server.html) [pages](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Deployment_Guide/s2-bind-zone.html) were useful in helping me find what I needed and gave examples to follow for formatting, etc.
- DNS services are enabled in `/etc/host.conf`. I looked at this file (with nano), but didn't need to change any of it.
- Zone files for individual domains are stored in `/var/named`. In this case, the one I wanted was in `/var/named/masters`.  In there, I found the opensmc file, and followed the existing formatting to add the proper MX servers, as well as some CNAME records for subdomains we'll use with google apps.
- I also found this neat little tool for checking that the settings have gone through: [https://toolbox.googleapps.com/apps/dig/].  (Can also be done via terminal with the `dig` command, e.g. `dig opensmc.org MX`)

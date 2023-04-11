---
title: "over and out"
date: 2023-02-11T01:39:27-08:00
draft: false
description: further progress on more blog backend work.
---

A busy and humbling week and a half. Let's get accomplishments out of the way:
- Replaced the default NGINX 404 page (try it out!)
- Continued work on the Linode playbook
    - Added CertBot tasks
    - Replaced some copy tasks with synchronize/rsync ones for efficiency
- Continued setting up CloudFlare Load Balancing
    - Added the Linode instance's IP in the failover pool

Now for the humbling part. Lessons learned:
- You cannot simply copy over `/etc/letsencrypt` over to the failover server.
- CertBot issues certificates for the failover server as "nate.unpass.net-0001".
    - Doing so also affects the NGINX config, meaning I will probably have to start using Jinja2 templating to bypass that. 

Admittedly, I don't know where to proceed from here. I've spent days pulling my hair out over how to get this active-active setup to work. Given the *nook* has never had unscheduled downtime, I probably don't have to worry about *automatic* failover. But the prospect of having a "self-healing" setup with Linode is too good for me to give up. For now, I'm taking a break from backend work. If you have any suggestions, don't hesitate to shoot me an email or Discord message!

Despite those shortcomings, I'm proud to see that the core of the blog is fully functional. Yes, it is a static site. But the learning process has been fun, and getting DNS, SSL certs, and Git to work feels rewarding beyond words. Blogging the process with so much transparency has been therapeutic for me, and I hope you've gotten some insight amidst all the noise! Broader and more fun posts are on the horizon.

cheers,\
-nate

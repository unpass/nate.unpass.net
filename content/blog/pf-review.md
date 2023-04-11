---
title: "aliexpress pfsense fw mini-review"
date: 2023-04-10T15:30:46-07:00
description: reviewing a pfSense firewall I bought from AliExpress
draft: false
---

Hello!

It's been a while, but after a busy March I've finally come around adding to the home server. This time, we'll be
looking at a [firewall](../images/pf.jpg) I got from AliExpress.

How I hadn't realized that using an antiquated ISP router to protect an exposed web server is a terrible idea earlier
is beyond me. Better late than never! I had played around with pfSense through a VirtualBox network before, mainly
as a lab for a Udemy course. But actually putting down hardware in a real SOHO is a lot more fun.

On a hardware level the Ali router is pretty adequately featured, with a couple of USB 2 and 3 ports, HDMI *and*
DP ports, 4 Ethernet ports, and even antennae holes bored for WiFi potential. Standard, but far more than what the
Nook and ISP router have.

I opted to have it shipped with pfSense pre-installed, but the installation guide is very well-documented that
the average person shouldn't mind being able to shave off a few bucks. With that out of the way, let's go over my
set up.

I do like having the ISP router as a gateway, so rather than having to reconnect every wireless device in the house
to the pfSense firewall I went for the *bridge mode* route, so that devices on the pfSense router still have gateway
access (with the ability to be on their own subnet!). Initially, I was going to use the router as a L2/"transparent"
firewall, but ultimately decided that only stopping attacks at the Data Link layer is useless, even if it means
conveniently having my server on the ISP subnet. Thankfully, AT&T is nice and allows for
["IP Passthrough"](https://downloads.linksys.com/downloads/image/SF293959-004_EN_v1.png), so we
can proceed with having a fully-functional firewall on another subnet.

[Here](../images/pfbridge.png) is how I segmented the firewall. Since I'm still attaching the WAN to the AT&T gateway, it made more sense
to bridge the LAN ports on the Ali router. After some necessary Allow rules, we were in business.

The rest is typical pfSense stuff. The dashboard is nice, and the UX overall is very intuitive. Doesn't feel like it was designed by a
government acronym company, which is all you could really ask for. Since the setup, there hasn't been a single hiccup.
The firewall is bulletproof (more so than AT&T's), and being able to look at logs and
export config files is a luxury. Couldn't be happier.

It's no enterprise-grade hardware, but 100 bucks for a fanless out-of-the-box firewall works for me!

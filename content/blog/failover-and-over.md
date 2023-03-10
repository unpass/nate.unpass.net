---
title: "failover and over"
date: "2023-01-30T04:26:44-08:00"
description: "figuring out cloudflare's load balancer with linode and ansible"
---

## hello again!

I noticed that CloudFlare has this option for load balancing and thought, "Why not use it?"

I've been spending the past week learning how I can quickly deploy cloud instances for the blog as backup. Ansible has been a great friend for this. Being already familiar with docker-compose yamls, I was able to step into playbooks with a fair amount of confidence. As of writing, the playbook can set up the site, but I'm still figuring out how to automate SSL certificates to make CF happy. In the meantime, you can check out the playbook [here](https://github.com/unpass/yamls). It's a bit ugly at the moment, but the yaml repo is largely meant for showcasing and critique.

As for the cloud hosting aspect, I opted for [Linode](https://nate.unpass.net/images/linodedash.png). I played around with AWS, and while their free tier is very generous with Debian EC2 instancing it's got some caveats. Imagine having to pay for static addressing! I've also heard [horror stories](https://www.reddit.com/r/aws/comments/g1ve18/i_am_charged_60k_on_aws_without_using_anything/) regarding billing and would rather not take my chances with something as simple as a static site. Especially when $5/month gets you the convenience of Linode's "set-it-and-forget-it" business model. 

I hope to share the final product soon. Ansible has been really fun to learn, and I can't wait to use it to grow the *nook* lab beyond a simple game server and blog.

cheers,\
-nate


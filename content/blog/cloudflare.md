+++
title = "cloudflare and ssh galore"
date = "2023-01-24T15:10:47-08:00"

#
# description is optional
#
# description = "An optional description for SEO. If not provided, an automatically created summary will be used."

tags = []
+++

Just migrated all of the blog's DNS records over from Google to CloudFlare and I gotta say, I'm really impressed.

For starters, the less power Google has over me, the better. Plus I don't think it's worth using their "domains" services outside of the name lease as it's quite featureless. I'm not a paid shill for CF but there are so many useful features on the free tier alone
- Wayback archiving
- Basic bot/DDOS protection (I'd add a rate limiting method on top of this)
- Location-based firewall rules
- Catch-all email addresses for dropping unwanted spam
- Analytics that don't rely on Google

The only bump along the way was getting LetsEncrypt and CF's "full (strict)" SSL/TLS mode to get along with each other,  but that's what `certbot --nginx` is for.

On top of DNS adventures, I took on the liberty of hardening SSH a bit more with public keys. I'd like to thank whoever decided to bundle Windows with OpenSSH a few years ago, because I'd rather not use PuTTYgen again.

So that's that. I could probably throw in a more robust reverse proxy solution and Docker into the mix, but I don't think the blog gets that much attention [(hello world!)](../images/cfmap.png) to warrant that much extra overhead. [Cloud provisioning however...](https://nate.unpass.net/failover-and-over)

cheers,\
-nate

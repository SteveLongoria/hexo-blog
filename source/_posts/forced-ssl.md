---
title: "'I enabled SSL but when I type in my URL it still shows only HTTP'"
date: 2018-07-30 21:48:14
tags: [Forced, SSL, HTTP, HTTPS]
---

I had a client recently tell me that they bought an SSL certificate and that their site was now secure.

I of course, went and typed in 'theirdomain.com' to see if this was true, and sure enough it showed the site as being unsecure still with 'http' in the address bar.

They did indeed have an SSL certificate activated on their domain but the problem here is that they didn't have 'Forced SSL' implemented.

Forced SSL is when your site goes to the secure version (HTTPS) of your site no matter if the visitor types:
www.yourdomain.com
yourdomain.com
http://yourdomain.com
http://www.yourdomain.com. 

Basically, it doesn't matter how the visitor types in your domain (so long as it's spelled correctly and has the correct top-level domain) they'll reach the secure (HTTPS) version of your site.

The easiest way to achieve this is to use [Cloudflare.com](cloudflare.com).

Cloudflare offer's a free SSL with their free membership level.

Once you switch your DNS over to Cloudflare by following the simple instructions after joining, you'll simply need to setup a "Page Rule" inside Cloudflare to enable Forced SSL.

<center>{% asset_img forcedsslcloudflare.png Cloudflare Page Rule %}</center>

It's as simple as inserting 'http://*yourdomain.com/*' under the "URL matches" section of the Page Rule creation process and "Always use HTTPS" under the last section of the Page Rule creation process as shown in the image above.
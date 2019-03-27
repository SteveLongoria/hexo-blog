---
title: Should you track your subdomain blog separately in Google Analytics?
date: 2019-03-27 14:22:56
tags: [blog, subdomain, google-analytics, analytics]
---

Many people decide to host their blog or shop on a sub-domain like blog.domain.com or shop.domain.com. From a developer standpoint it's often nice to be able to keep each Content Management System separate from each other, which is why this is a common setup.

One question that first comes up in these cases is whether or not you should track each sub-domain as a separate property inside Google Analytics or do [cross-domain tracking](https://support.google.com/analytics/answer/1034342?hl=en). For those who aren't sure what that is, it's when you have a unified analytics report showing traffic to multiple domains (or sub-domains) as one site instead of separate sites.

I had to make this decision recently since I have my main site hosted at stevelongoria.net and the blog hosted at blog.stevelongoria.net. I chose to setup cross-domain tracking in order to have more accurate data. Having each domain setup as it's own property in Google Analytics often results in you counting the same visitor twice, like in my case when visitors clicked thru from stevelongoria.net to blog.stevelongoria.net, Google Analytics would count that as two separate visitors when the reality is it is one single visitor.

Having them setup as separate Google Analytic properties also makes it difficult to see the original referral source in many cases when visitors jump back and forth between the two domains.

These are the main reasons why I decided to setup cross-domain tracking on my site! I recommend you do the same if you find yourself having multiple domains and sub-domains.
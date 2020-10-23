---
title: How to connect your HTML contact form with Mailchimp
date: 2019-10-03 10:02:36
tags: [mailchimp, contact-form, html]
---

I was recently setting up a new lead generation website for a tree trimmer client and I had to decide how to wire up the contact form since I was creating a static HTML site and hosting it for free on Netlify. 

It had to be a no-cost solution and allow for custom thank you page redirects so I can track Google Ad conversions. That means Typeform and Formspree were not options. 

I normally use [Drip](https://drip.com) but this client didn't need the extra functionality Drip provides and their free tier maxes out at 100 subscribers, whereas with MailChimp you get 2k subscribers for free.

So I went searching in Google for 'mailchimp raw html form' and the like. I didn't want to embed the MailChimp form, that's something entirely different. We just need to know what elements to add to our existing HTML form so when a visitor submits their information it is sent to MailChimp. 

It was actually hard to find the right documentation page to reference since the wording they actually use is ['Host Your Own Sign Up Forms'](https://mailchimp.com/help/host-your-own-signup-forms/).

That walks you through how to 'wire up' your own HTML form so it subscribes people to whatever MailChimp audience you want. It's super easy!


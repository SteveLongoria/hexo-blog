---
title: How To Track Offline Sales Conversions From Google Ad Clicks
date: 2018-10-02 15:52:36
tags: [Offline, Sales, Conversion, Google, Ad, Clicks, Adwords, Conversion, Tracking]
---

It's easy to track sales conversion when you're sending ad traffic to an ecommerce store or sales funnel where payments are handled online. 

What if your business handles sales offline? It's not so easy to track OFFLINE sales conversions now is it?

I had this challenge over the past year as I've helped several property managers with their Google Ad campaigns. For the most part, they're satisfied with just optimizing the campaign based on a cost per call or lead basis, but the holy grail is being able to track offline sales conversions back to the ad, zip code, keyword, time of day, day of week and device.

This way you can optimize the campaign more effectively to maximize your return on investment. I mean, just imagine if you knew exactly which ad, zip code, keyword, time of day, day of week and device generated the best ROI. Well, the answer is you could adjust bids accordingly to maximize your return on investment.

Fortunately [Google introduced their offline sales conversion solution](https://support.google.com/google-ads/answer/2998031?hl=en) back in 2015. Setting it up is different based on if your campaign is generating calls or clicks. It also requires a little JavaScript knowledge.

<h3>Setting Up Offline Sales Conversion Tracking For <u>Clicks</u></h3>

First you need to enable Auto-tagging in your Google Ads account. When you do this, each visitor that comes to your website from the Google Ad is tagged with a unique 'Google Click ID' or 'gclid' for short. This tag comes in the form of something called a query string parameter. Have you ever seen a weird string of letters and numbers at the end of a URL that starts with a question mark?

It looks just like this:

<center>{% asset_img querystringparameter.png Query String Parameter %}</center>

Now here's the challenging part, especially if you don't know JavaScript, for every Google Ad visitor you'll need to automatically grab that unique Google Click ID from the URL and insert it into a hidden field in your form. 

You can achieve this by importing [these JavaScript files found int his repo](https://github.com/travishorn/qs) and inserting the following bit of JavaScript code just above the </body> tag on your page:

<center>{% asset_img jscode.png JS Code %}</center>

After you have that setup, every Google Ad visitor that fills out that form and submits it will now have their unique Google Click ID sent along with their name, email, etc. You'll want to store this info in a CRM and keep track of sales using that CRM. You then export and upload this CRM data to Google Ads every month and Google will connect the dots for us so to speak.

That's it, go implement this in your campaigns and let me know how you fare! In my next post I'll explain how to setup Offline Sales Conversion Tracking for calls so stay tuned!


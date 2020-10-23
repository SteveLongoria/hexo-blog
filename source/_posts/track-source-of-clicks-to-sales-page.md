---
title: Is there any way to track the source of clicks to your sales page?
date: 2019-09-08 19:11:45
tags: [utm-parameters, google-analytics, sales-tracking]
---

I was recently asked this question by somebody who had 100+ Youtube videos all driving traffic to his products sales page on his website, linking to the sales page in the video's description or via video card.

He wanted to know which video was giving him his best sales conversion. He didn't think it was possible to do this kind of tracking with Google Analytics and he was looking for 3rd party services like Bitly. 

The truth is, you can achieve this level of tracking easily with Google Analytics by using something called UTM parameters. It's also better because users can still see the destination URL when they place their cursor over the hyperlink. 

With Bitly links, this is hidden and therefore makes some users more hesitant to click on the Bitly link because they don't know where they're going to be sent!

The first step is to set up the UTM parameters, which you can do using this [URL builder tool](https://ga-dev-tools.appspot.com/campaign-url-builder/) Google created.

So for example, this person who had 100% Youtube videos would setup his UTM parameters like this:

![Bidding](/content/utmparameters.jpg)

He'd change the Campaign Name section for each video. This way he can identify exactly which video is giving him his best return on investment. If you didn't want the long URL, you can create a vanity URL to shorten it to be something like 'yourdomain.com/vanity-url'.

Now assuming he has a Google Analytics Goal already set up for the sale of his product, he can now easily see which video is giving him his best conversion rate by going to Acquisitions > Campaigns inside Google Analytics. 

UTM parameters are useful for tracking ANY external link pointing to your site in order to give you better insights; emails, social media, print, etc.
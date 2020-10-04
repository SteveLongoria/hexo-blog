---
title: The Easy Way To Accept Credit Card Payments On Your Website
date: 2020-10-03 13:29:02
tags: [payment-processing, stripe, web-development, sales-funnel]
---

I haven't launched many ebooks to date, but when I have I typically would use Gumroad. It was just the easiest way to accept credit card payments and deliver my ebook. The downside is that they take 15% per transaction, and the load time for the pop-up modal is horrible.

There are other 3rd party solutions I could use but they would have me paying a monthly price just to integrate with the Stripe API and accept credit card payments on my website.

[I learned to code just to be able to work with the Stripe API directly.][1] This way I wouldn't have to rely on 3rd party services as much. This setup still required server-side hosting which is going to cost you about $10/mo starting.

You may say, "Well that's not bad Steve! It's only $10/mo!".

This is true, and if your website or app already utilizes a backend server then it's not a big deal.

If you just have a static website or you're using Webflow with basic hosting (non-ecommerce plan) like me, however, then it's a bigger hassle.

Also, learning how to code so you can work directly with the Stripe API is probably not something you want to do or are willing to do.

So what's a guy or gal to do?

Sure, I could upgrade my Webflow hosting to their Ecommerce plan but that takes my hosting bill from $15/mo to $42/mo.

I must confess, I'm somewhat obsessed with figuring out how to bootstrap a business online with as little money as possible.

Paying monthly for SaaS products can add up over time so anywhere you can save some money helps.

I'm happy to announce that [Stripe finally has made a way to create a simple, beautiful checkout without needing to use any server-side code][2].

I'm currently using it to sell [this ebook][3] if you want to see how the checkout looks. :)

You just embed some 'client-side' code on your website, style the button to match your website and you're ready to accept credit card payments for your digital product. Simple as that!

You can set up the 'thank you' page where customers are redirected to after making payment. Which is a great place to have a download button so they can download the ebook they just purchased.

You can set up a webhook between your email services provider like Drip.com or Convertkit and Stripe so you can put them through whatever type of email marketing automation you desire.

I found it easier to just set up a Zapier Zap syncing Stripe with my email service provider but either way works.

[1]: https://blog.stevelongoria.net/2019/02/26/setup-stripe-checkout-using-expressjs-heroku/
[2]: https://stripe.com/docs/payments/checkout/client
[3]: https://www.stevelongoria.net/products/google-ad-advantage

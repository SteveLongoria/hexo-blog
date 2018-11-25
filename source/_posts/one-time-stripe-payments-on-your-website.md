---
title: How To Accept One-Time Payments Using Stripe On Your Website
date: 2018-11-25 12:13:28
tags: [Stripe, Payments, Checkout, Website]
---

You want to be able to process just a simple one-time payment for your product using Stripe but you have no clue how to do it. 

You tried reading their documentation but you're having trouble understanding it because let's be honest, you're NOT a web developer!

I made [a blog post here](https://varpop.com/stripe-checkout-expressjs-one-time-charge/) on my other site called Varpop.com explaining my experience setting this up and what I did to overcome obstacles I encountered while setting up Stripe Payments using NodeJS.

Unfortunately, you're probably going to have to learn a little bit about entering commands into your computer terminal and some HTML & JavaScript to even understand my blog post.

After you follow the instructions in that post, you'll still need to deploy or upload your NodeJS app (i.e. your website that processes payments using Stripe API) to the Internet using [Heroku](https://heroku.com). I wrote a post about this [here](https://varpop.com/deploy-nodejs-express-app-heroku/).

Don't forget to switch out your Stripe Development API Keys for your Production API Keys before deploying.

If you're existing site doesn't use NodeJS for it's server-side language, you may need to setup your NodeJS/Stripe payment app on a sub-domain. Something like https://pay.yourdomain.com. Or you can use whatever server-side language your existing site uses to integrate with Stripe, like PHP, unfortunately I only specialize in Stripe/NodeJS integrations so I won't be able to help you with those.
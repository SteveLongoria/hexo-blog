---
title: How To Setup Recurring Payments With Stripe Checkout
date: 2019-03-12 09:05:59
tags: [stripe, checkout, recurring-payments, subscriptions]
---

Just a couple weeks ago I wrote a step-by-step guide showing you [how to setup Stripe Checkout using Express.js and Heroku](https://blog.stevelongoria.net/2019/02/26/setup-stripe-checkout-using-expressjs-heroku/). This guide only showed you how to setup one-time payments, but what if you want to setup recurring payments so you can sell subscriptions?

You're in luck, I'll show you how to set this up today in this post!

First, if you haven't yet, go ahead and go through this guide and setup Stripe Checkout with one-time payments. If you already have that setup, it's only a small change to setup recurring payments instead of the one-time payment.

After that's setup, we need to [create a product and pricing plan inside our Stripe Dashboard](https://stripe.com/docs/billing/subscriptions/products-and-plans)!

<center>{% asset_img stripeproductplan.png Stripe Product & Plan %}</center>

After creating your product and plan, you'll want to snag the ID for your plan. It'll look like this 'plan_DguBnFdeQ27pja':

<center>{% asset_img stripeplanid.png Stripe Plan ID %}</center>

Now the fun part! We need to change some javascript code in the app.js file.

Currently, after following [this guide](https://blog.stevelongoria.net/2019/02/26/setup-stripe-checkout-using-expressjs-heroku/), you'll have this bit of code here on lines 22-37 in the app.js file. 

{% codeblock myapp/app.js lang:javascript %}


app.post("/charge", (req, res) => {
  let amount = 500;

  stripe.customers.create({
     email: req.body.stripeEmail,
    source: req.body.stripeToken
  })
  .then(customer =>
    stripe.charges.create({
      amount,
      description: "Sample Charge",
         currency: "usd",
         customer: customer.id
    }))
  .then(charge => res.render("charge.pug"));
});

{% endcodeblock %}


This code obviously makes only a one-time payment, so we need to change it to the following:

{% codeblock myapp/app.js lang:javascript %}

app.post("/charge", (req, res) => {

stripe.customers.create({
     email: req.body.stripeEmail,
    source: req.body.stripeToken
  }).then(customer => 
  stripe.subscriptions.create({
  customer: customer.id,
  items: [{plan: "plan_yourstripeplanID"}],
})).then(charge => res.render("charge.pug"));
  
  });
  
{% endcodeblock %}


You'd replace 'plan_yourstripeplanID' with your Stripe plan ID you got from earlier.

That's it! Go ahead and test out your Stripe Checkout form to make sure it's now making recurring payments [by using a test card](https://stripe.com/docs/testing#cards).

If it's all working correctly, go ahead toggle out of 'Test View' mode inside your Stripe Dashboard to go into live mode. Then you're going to have to setup your Product and Plan again add your live mode plan ID to your code like shown above. 

It's kind of confusing how you have to jump between test mode and live mode but that's just how Stripe works. You are in test mode when you're developing your checkout form and testing it, then you have to switch to live mode when you're ready to real payments from customers. You can [read more about it here](https://stripe.com/docs/keys#test-live-modes).

What are you waiting for!? Go setup recurring payments and start selling some subscriptions! :)


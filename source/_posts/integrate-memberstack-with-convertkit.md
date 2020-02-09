---
title: How to Integrate Memberstack with Convertkit
date: 2020-02-08 19:41:01
tags: [membership-sites, memberstack, convertkit, marketing-automation]
---

So you just set up a sweet new membership site using [Memberstack](https://memberstack.io) ([aff link](https://memberstack.io/?via=steve)). Now you want to start setting up marketing automation sequences inside [Convertkit](https://converkit.com). To do this you need to automatically sync new member data to your Convertkit account. 

If you only have one membership level, this is easy peezy. Just use the  [Memberstack Zapier integration](https://help.memberstack.io/post/zapier). If, on the other hand, you have multiple membership levels, like say Basic, Premium and Gold. 

The Memberstack Zapier Integration currently won’t let you specify which plan they’re on. This means you can only tag them as a “Member” inside Convertkit and that’s it. Ideally, you want to be able to tag them based on the membership level they signed up for; Basic, Premium or Gold.

I believe [they're working on this issue](https://forum.memberstack.io/t/zapier-membership-subscribed-to-missing-on-update/141/4), but in the meantime, you'll have to use a workaround; the [Convertkit Stripe Integration](https://help.convertkit.com/en/articles/2632323-stripe-integration).

Once you integrate your Stripe account with your Convertkit account, you can then tag and set up automations based on which membership level they're subscribed to.

You may be wondering, “*Well can't I just use the Convertkit Stripe Integration exclusively? Why do I need Zapier?*“

The reason you need both at the moment is because the Convertkit Stripe Integration won't send over all of the custom field attributes you collect from new members upon sign up. Like the customer's first name and last name for example. 

To collect all of the custom field attributes you'll need to set up the [Memberstack > Convertkit Zapier zap](https://help.memberstack.io/post/zapier).

It sucks we can't just use one integration but it is what is for the time being. Either way it gets the job done!
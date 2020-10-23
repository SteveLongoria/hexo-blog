---
title: The Easiest Way To Integrate Drip Into Your Ghost Blog
date: 2018-07-28 10:46:32
tags: [ghost, blog, drip, ecommerce, crm]
---

**Note: If you're looking to put a contact form on your Ghost blog, you actually want to [read this blog post](https://blog.stevelongoria.net/2019/03/10/how-to-setup-a-ghost-blog-contact-form/)!**

[Ghost](https://ghost.org/) blogs have a built in subscription feature which allows people to optin to your newsletter. Currently you can only Import CSV, Export CSV or Add Subscriber individually.

<center>{% asset_img ghost-subscribe.png Ghost Subscribe Options %}</center>

You still have to have a 3rd party software for emailing out to your list, something like [Drip](https://www.drip.com). You can of course sync with a bunch of marketing automation and email marketing software like Drip by using their Zapier integration, but that's added cost where it's just not needed.

What I'm going to show you in this post is how to integrate Drip into your Ghost Blog so you don't have to pay for zaps via Zapier integration.

The easiest route for most is going to be simply using the Drip Form Widget and install it site wide on your Ghost Blog. 

You can find the javascript snippet after inside your Drip dashboard under Account > Site Setup:

<center>{% asset_img dripjssnippet.png Drip JavaScript Snippet %}</center>

We're going to inject this code into our Ghost blog by using the 'code injection' feature under Settings inside your Ghost dashboard:

<center>{% asset_img ghostcodeinject.png Ghost Code Injection %}</center>

Now all you have to do is [create a new Drip Form Widget](https://help.drip.com/hc/en-us/articles/115003730671-Create-a-Form) inside your Drip dashboard. You can control exactly which pages the widget shows up on, how often it shows up, etc.

## But I Hate Pop-ups Steve, I Don't Want A Pop-up!

I hear ya, I'm not a big fan of pops either. I prefer having my optin forms embedded into my pages or as a pop-up modal that is only triggered when the user clicks a button or link. You can actually do the pop-up modal using the Drip Form Widget but I found it to be inconsistent, it would pop-up most of the time when the button was clicked but not other times.

I decided to just create my own custom styled optin form embedded in the page. You can read about how I set that up [here in this post](https://blog.stevelongoria.net/2019/01/17/custom-drip-optin-form-ghost-blog-theme/). 

**Drip Hosted Form**

Before I setup the custom optin form and embedded it in the page, I simply hardcoded some links in the Ghost Theme to point a Drip form that was hosted by Drip. You can see an example of the Drip hosted optin form [here](https://www.getdrip.com/forms/849303961/submissions/new?).

Here are the files and code I changed in order to get my homepage newsletter sign up button and "Subscribe" nav link to point to the Drip hosted form (click on the images to view the code change in Github):

<center><a href="https://github.com/SteveLongoria/varpop/commit/5fa6c24d2becd498b270fc3d42cd0e6b39782316" target="_blank">{% asset_img indexnavghost.png Ghost Index & Nav Changes %}</a></center>

Here's the code I changed on the post.hbs template so the newsletter sign-up call to action shows up at the bottom of each blog post:

<center><a href="https://github.com/SteveLongoria/varpop/commit/746880625c1c94a9624b31bb6872c047f66e4a17" target="_blank">{% asset_img ghostposttemplate.png Ghost Post Template %}</a></center>

And that's it, those are all of the top ways to integrate Drip into your Ghost blog. The Ghost theme I was using for Varpop is [Attila theme](https://github.com/zutrinken/attila) FYI.

Next, [download the ultimate guide to SEO for bloggers](https://stevelongoria.net/guides/blog-traffic-guide).

## Related Posts

[How To Create A Contact Form For Your Ghost Blog](https://blog.stevelongoria.net/2019/03/10/how-to-setup-a-ghost-blog-contact-form/)
[How To Add A Custom Drip Email Optin Form To Your Ghost Blog Theme](https://blog.stevelongoria.net/2019/01/17/custom-drip-optin-form-ghost-blog-theme/)
[How To Create A Custom Drip Optin Form Using CSS Flexbox](https://blog.stevelongoria.net/2018/11/03/custom-drip-form-css-flexbox/)
---
title: The Easiest Way To Integrate Drip Into Your Ghost Blog
date: 2018-07-28 10:46:32
tags: [Ghost, Blog, Drip, Ecommerce, CRM]
---

**Update: I published another blog post showing how to embed a custom Drip email optin form directly into the Ghost blog theme. [Click here](https://blog.stevelongoria.net/2019/01/17/custom-drip-optin-form-ghost-blog-theme/) to read it!**

[Ghost](https://ghost.org/) Blogs have a built in subscription feature which allows people to optin to your newsletter. Currently you can only Import CSV, Export CSV or Add Subscriber individually.

<center>{% asset_img ghost-subscribe.png Ghost Subscribe Options %}</center>

You still have to have a 3rd party software for emailing out to your list, something like [Drip](https://www.drip.com). You can of course sync with a bunch of marketing automation and email marketing software like Drip by using their Zapier integration, but that's added cost where it's just not needed.

First I tried just adding the Drip Form Widget with 'Lightbox' Orientation and a time delay. This solution worked only when I was testing in my local Ghost development environment, when I uploaded the modified theme to my live Ghost blog though the widget wasn't working. I'll have to contact support about this but the in the meantime, that lead me down another path.

I then considered just creating a [subscribe.hbs Ghost template](https://themes.ghost.org/docs/subscribe-context) file and embedding the Drip Form but that would require me to do custom style job with CSS and I admittedly do not have a ton of experience styling forms. I then just decided to hardcode links into the Ghost theme to send people to the Drip Hosted Form that you can see [here](https://www.getdrip.com/forms/849303961/submissions/new?).

Here are the files and code I changed in order to get my homepage newsletter sign up button and "Subscribe" nav link to point to the Drip hosted form (click on the images to view the code change in Github):

<center><a href="https://github.com/SteveLongoria/varpop/commit/5fa6c24d2becd498b270fc3d42cd0e6b39782316" target="_blank">{% asset_img indexnavghost.png Ghost Index & Nav Changes %}</a></center>

Here's the code I changed on the post.hbs template so the newsletter sign-up call to action shows up at the bottom of each blog post:

<center><a href="https://github.com/SteveLongoria/varpop/commit/746880625c1c94a9624b31bb6872c047f66e4a17" target="_blank">{% asset_img ghostposttemplate.png Ghost Post Template %}</a></center>

And that's it, I've got Drip 'integrated'. The theme I'm using for Varpop is [Attila theme](https://github.com/zutrinken/attila).

Obviously the best long-term situation would be to just create a subscribe.hbs file and style the embedded Drip form to match your website's design. Also, it would be awesome if the Drip widget worked, I'll make an update if I learn more about that from support.
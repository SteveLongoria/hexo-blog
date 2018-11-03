---
title: How To Create A Custom Drip Optin Form Using CSS Flexbox
date: 2018-11-03 14:37:31
tags: [CSS, Flexbox, Drip, Marketing, Automation, Custom, Form]
---

I switched over to [Drip](https://getdrip.com) from [MailChimp](https://mailchimp.com) this past year for my email marketing/marketing automation solution and so far I'm really loving it! 

I haven't been a big fan of the Drip Form Widgets simply because I don't like pop-ups. I also like to have full control over how the optin form functions and how it looks. I personally like inline forms, where you just have the form on the page like I have on my blog if you scroll down to the bottom. I also like 2-step optin where the visitor clicks on the button and it opens up a pop-up window to optin. This is how I prefer to do pop-ups simply because they're "user initiated". The visitor decides when the pop-up appears.

In this post I'm going to show you how to create a custom 'inline' email form to sync with your Drip account. 

It'll look something like this by default but you can customize however you'd like:

<center>{% asset_img flexboxform.png flexboxform %}</center>

## Create Your Form

When you create your form, simply disable the widget option and click on the "Embedded" tab:

<center>{% asset_img dripembedform.png Embed Form Code %}</center>

## Snag Your Form ID Number 

Your going to want to snag your Drip Form ID number which is located in HTML code Drip gives you to embed, it is a 9 digit number and you'll find it in the "action" attribute in the "form" element:

<center>{% asset_img dripformid.png Drip Form ID %}</center>

## Copy & Paste This HTML & CSS Code

[Go to this Codepen project](https://codepen.io/stevehl25/pen/KrKxMx) where I already did the hardwork for you and copy and paste it into your project. Insert your Drip Form ID you snagged already and insert in the spots labeled with X's:

<center>{% asset_img codepen.png codepen %}</center>

Now just customize the colors and fonts to match the design of your site.

That's it! Go ahead and test out your new form to make sure it's working and you're good to go!

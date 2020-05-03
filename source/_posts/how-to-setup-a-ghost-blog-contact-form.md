---
title: How To Setup A Ghost Blog Contact Form
date: 2019-03-10 13:06:55
tags: [Ghost-Blog, Contact-Form]
---

Ghost is a great blogging platform but one thing it doesn't have setup 'out of the box' is a contact form. 

How frustrating! 

Fortunately, I'm going to guide you in the right direction so you can setup your Ghost blog contact form lickety split!

I have two options for you, a simpler option and a more complicated one depending on how you want to implement this.

## Simpler Option

I've recently been a big fan of using [TypeForm](https://typeform.com) for my contact form. It's free if you're just wanting a simple contact form and has such a nice user experience. Creating a contact form is simple with TypeForm, it's basically like creating a Google Form which is really easy. 

Once you create the form, it'll exist at a URL like 'yourbusinessname.typeform.com'. To integrate into your Ghost Blog, all you have to do is make a small edit to the theme. Simply add a html for the 'Contact' navigation link to the theme and point it to your TypeForm URL. Easy Peezy!

If you don't want to edit the theme, you can use [Ghost URL Redirects](https://ghost.org/tutorials/implementing-redirects/) here to redirect visitors to your new TypeForm contact form.

## More Complicated Option

**Step 1** 

[Create a new static page](https://docs.ghost.org/concepts/pages/) on your Ghost Blog and call it "Contact". 

**Step 2** 

Create a custom contact page template following the instructions [here in Ghost Documentation](https://docs.ghost.org/tutorials/custom-page-templates/). 

This will allow you to add custom CSS for the Contact Page! 

[Here's a great contact form using CSS & HTML](https://www.w3schools.com/howto/howto_css_contact_form.asp). You can use the CSS to make your custom contact page Ghost template.

The HTML from the form you'll use inside your Ghost Blog editor. You'll go back to the page you created in Step 1 and [insert the HTML into via the Ghost Editor](https://docs.ghost.org/faq/using-the-editor/). Don't forget to select your new custom contact page Ghost template to style up the form with the CSS. 

You can select the custom template using the dropdown menu found inside the post settings:

<center>{% asset_img ghostdropdown.png Ghost Dropdown Menu %}</center>

**Step 3** 

Now all you have to do is follow the steps at [Formspree.io](https://formspree.io) to 'wire up' your form to send to your email inbox. It's really simple, you basically just edit the form 'action' attribute with their URL followed by your email address you want the contact form messages sent to.

That's it! You're all done. You now have a nifty, mobile responsive contact form for your Ghost Blog or anything really! :)

[![Bidding](/content/blogtrafficguidebanner.jpg)](https://www.getdrip.com/forms/482178116/submissions/new)

**Related Blog Posts**
[Should You Submit Each New Blog Post To Google For Indexing?](https://blog.stevelongoria.net/2019/02/16/should-you-submit-each-new-blog-post-to-google-for-indexing/)
[How To Add A Custom Drip Email Optin Form To Your Ghost Blog Theme](https://blog.stevelongoria.net/2019/01/17/custom-drip-optin-form-ghost-blog-theme/)
[The Easiest Way To Integrate Drip Into Your Ghost Blog](https://blog.stevelongoria.net/2018/07/28/drip-ghost-blog/)
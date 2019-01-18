---
title: How To Add A Custom Drip Email Optin Form To Your Ghost Blog Theme
date: 2019-01-17 20:13:45
tags: [Ghost, Blog, Theme, Email, Optin, Form, Drip, CRM]
---

Blogging with [Ghost](https://ghost.org) is awesome and it does have built in email list building functionality so you can build an email list from your blog. The problem is that if you want those subscribers automatically sent to your favorite marketing automation software like [Drip](https://www.drip.com) or [ConvertKit](https://convertkit.com) you'll need to use [Zapier](https://zapier.com). This presents an added cost for each subscriber that opts in.

This can easily be avoided by adding your own [Drip](https://www.drip.com) form directly to your Ghost theme. This requires you to edit the code a bit but don't worry, I'm going to walk you through this!

The theme I was using to make this edit was the [Atilla theme](https://github.com/zutrinken/attila). If you have a different theme it shouldn't be that different but if it is feel free to contact me for help. This short guide is assuming you already have the basic [Drip JavaScript Snippet](https://help.drip.com/hc/en-us/articles/115003737152-Install-Your-JavaScript-Snippet) already installed on your website.

<h3>Step One</h3>

You need to create a new Drip form because we'll need to snag the form number to embed in our code. 

When you create the Drip form go ahead and disable the widget, we won't be needing it. The number you want to snag is right here, you don't even need the rest of the code, just the number:

{% asset_img dripformcode.png Drip Form Code %}

<h3>Step Two</h3>

Add this code to your assets/css/style.css file:

{% codeblock assets/css/style.css lang:css %}
/* Web Form */
	
	*:focus {
	    outline: none;
	}	
	
	#subscribe-cta {
		margin: 20px 0 0 0;
	}
	
	input, #cta-btn {
	  font: inherit;
	  border: 1px solid #33adcc;
	  &:focus {
	    outline: none;
	  }
	}
	
	form {
	  display: flex; 
	  grid-column: 2;
	  justify-content: center;
	  margin: 10px 0 0 0;
	}
	
	input {
	  padding: 0.5em 0.75em;
	  width: 200px;
	}
	
	#cta-btn {
	  padding: 0.5em 0.75em;
	  color: #ffffff;
	  cursor: pointer;
	  background-color: #33adcc; 
	  width: 120px;
	  &:hover {
	  	background-color: #034b5b
	  }
	}
{% endcodeblock %}


<h3>Step Three</h3>

Add the web form on the homepage and anywhere else you want it! For example, I put it in my index.hbs file and post.hbs. Replace the X's with your Drip form number we snagged in Step One above:

{% codeblock lang:html %}
<div id="subscribe-cta">
<form action="https://www.getdrip.com/forms/XXXXXXXX/submissions" method="post" data-drip-embedded-form="849303961">
<input type="email" id="drip-email" name="fields[email]" value="" placeholder="Enter your email..."/> 
<button id="cta-btn" type="submit" data-drip-attribute="sign-up-button">SUBMIT</button>
</form>
</div>
{% endcodeblock %}

[Check out my exact changes to exact files in my Github commit here.](https://github.com/SteveLongoria/varpop/commit/fce2e8bc11c23ee55d58f9bd8702dfd6612ee633)
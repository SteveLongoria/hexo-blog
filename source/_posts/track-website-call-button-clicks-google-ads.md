---
title: Tracking Call Button Clicks On Your Website As A Google Ad Conversion
date: 2019-09-26 12:40:20
tags: [google-ads, conversion-tracking, call-conversion]
---

Many businesses are just looking for the phone to ring. Even in our modern age where we have chat bots and SMS text message marketing, phone calls are still one of the top communication channels for local businesses. Because of this it's important to accurately track website call conversions when running a Google Ad campaign for such a business.

Fortunately, Google Ads has [call conversion tracking](https://support.google.com/google-ads/answer/6100664?hl=en) you can add to your website. It will dynamically replace our phone number on the website or page with a Google forwarding number. 

The default setup doesn't track calls coming from people clicking on your phone number however, it only works if they read the number off your site and dial the number on their phone. That's no good considering most people will visit from a mobile device and you should have a 'click to call' button to make it easy for them to call.

You need to do some additional setup to track call button clicks on your website as a Google Ad conversion.

Here's how you do it!

You go to Conversions > Phone Calls inside Google Ads and you'll see these 3 options. 

![Bidding](/content/callconversion-1.jpg)

Select the 2nd one. You'll then be asked to enter all the basic info for the conversion like name, value, call time, etc.

![Bidding](/content/callconversion-2.jpg)

Now it's time for tag setup. We're going to install the tag ourselves, don't worry it's easy! 

![Bidding](/content/callconversion-3.jpg)

Make sure the global site tag is added first.

![Bidding](/content/callconversion-4.jpg)

Now the phone snippet part is where most people go wrong. They just select the first option because the second option sounds complex and scary. 

![Bidding](/content/callconversion-5.jpg)

Unfortunately, the second option is how we track call button clicks on your website.

So select 'Don't enter a number. You'll need to edit your website code manually.'

![Bidding](/content/callconversion-6.jpg)

Now instead of installing the phone snippet they give you, we're going to add the following instead and replace the 1-800 number with whatever phone number you're trying to track on your website:

{% codeblock lang:javascript %}

<script type="text/javascript">
    var callback = function(formatted_number, mobile_number) {
      // formatted_number: number to display,in the same format as
      //        'phone_conversion_number'.
      //        (in this case, '1-800-123-4567')
      // mobile_number: number formatted for use in a clickable link
      //        with tel:-URI (in this case, '+18001234567')
      var e = document.getElementById("number");
      e.href = "tel:" + mobile_number;
      e.innerHTML = "";
      e.appendChild(document.createTextNode(formatted_number));
    };
    gtag('config', 'AW-CONVERSION_ID/CONVERSION_LABEL', {
      'phone_conversion_number': '1-800-123-4567',
      'phone_conversion_callback': callback
    });
  </script>

{% endcodeblock %}

Remember this goes in the <head></head> just under your global site tag.

You also want to replace the 'CONVERSION_ID' and 'CONVERSION_LABEL' with yours. They'll look something like this 'AW-123456789/c8dIHF7W_YcBEM2H4dgD'.

Then you add id="number" to the <a> element you're trying to track.

![Bidding](/content/callconversion-7.jpg)

All of this is explained in [Example 3 of Google Ad Documentation here](https://support.google.com/google-ads/answer/6095883?hl=en) if you want to do some more reading.

That's it! You'll be all set and ready to rock after that.
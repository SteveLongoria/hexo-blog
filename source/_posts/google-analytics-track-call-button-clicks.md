---
title: How to track call button clicks as Goals in Google Analytics
date: 2019-10-07 15:59:08
tags: [google-analytics, analytics, conversion-tracking]
---

When setting up Google Analytics, most website owners fail to properly setup up Goals. This means they're only getting basic data on how visitors are finding your website, where they're from and what pages they went to. 

What if you want to track which visitors are clicking or tapping on your phone call button to call your business? This would allow you to identify which traffic sources or marketing campaigns are clicking the call button at a higher rate. This would then allow you to double down on the traffic sources or marketing campaigns that are generating the best cost per 'call' action.

You do this first by setting up what's called a 'custom event' in Google Analytics. This sounds a lot more complicated and difficult than it actually is. To track 'clicks' on a button or hyperlink as an 'event' in Google Analytics, all you do is add this attribute and 'gtag' function as the value to your <a> HTML element.

{% codeblock lang:javascript %}

onclick="gtag('event', 'click', {'event_category': 'Call Button'});"

{% endcodeblock %}

This is assuming you're using the gtag.js Google Analytics code on your website. This is where it can get confusing because if you try to Google about tracking custom events in Google Analytics, you'll find blog posts about how to implement using Google Analytics old Javascript library (ga.js and analytics.js). 

The most up to date one is [gtag.js](https://developers.google.com/analytics/devguides/collection/gtagjs/events), which means if you setup your Google Analytics code in your <head> tag yesterday or anytime in the past year, it's likely the gtag.js library you're using, which is what we want for this tutorial.

The full <a> element would look something like this:

{% codeblock lang:html %}

<a href="tel:+15413338888" onclick="gtag('event', 'click', {'event_category': 'Call Button'});">Call 541-333-8888</a>

{% endcodeblock %}

## Testing Out The Custom Event

Now that you have that setup, let's test it out! We want to make sure the event is firing before we do the final step of setting up the Google Analytics Goal. 

Open up your website in one tab and your Google Analytics dashboard in another. Be sure to view the Real-Time > Events report in Google Analytics. 
Now hop over to the tab that your website is loaded in and click on the button. You should be able to see the event register in the Real-Time > Events report inside Google Analytics.

## Setting Up Google Analytics Goal

Once the custom event is firing, it's time to setup a Google Analytics Goal around that custom event we just created. Head over to the Admin area of Google Analytics. It's the small gear icon in the bottom left hand corner.

Click on "Goals" under the Views column which is the farthest to the right. 

We're going to create a 'Custom' goal, then the 2nd step 'Goal Description' is to name the goal and select a 'goal type'. For the goal type we'll select 'event':

![Bidding](/content/gagoal-1.jpg)

For the 3rd step 'Event Conditions' we need to enter the following (assuming you used the same parameters I gave in the example above):

![Bidding](/content/gagoal-2.jpg)

Click save and you're all set! 

## Testing Out The Google Analytics Goal

You can test this in real-time just like we tested the event above, by opening up 2 tabs, your website in one and Google Analytics in the other. Click on the button and view the Real-Time > Conversion Report inside Google Analytics. It should show the new Goal firing! 

That's it! You now have more Google Analytic super powers!


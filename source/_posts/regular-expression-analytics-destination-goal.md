---
title: Should You Setup A Regular Expression Google Analytics Destination Goal?
date: 2018-10-29 22:12:24
tags: [google, analytics, regular, expression, destination, goal]
---

When setting up lead magnet "thank you" pages and Google Analytic goals, most will start by setting up a separate goal for each different offer and lead magnet they have. 

This quickly becomes tedious. Instead if you just begin all of your thank you page file names with the same set of numbers or letters, you can set a [regular expression Google Analytics goal](https://support.google.com/analytics/answer/1034324?hl=en). 

For example, let's say all of your lead magnet 'thank you' pages and offers all start off with "ty" in the file name, like "ty8202.html". 

You'd just make a regular expression Google Analytics goal called "Sign Up" and set it to "(ty)". Now whenever anybody lands on a page that has "ty" in the file name it will trigger this "Sign Up" goal. No matter if it's "ty8202.html" or "ty7281.html". 

Just be careful you don't accidentally include whatever character's you're using in the regular expression in non-thank you page file names. So in the case of the example, you'd need to make sure you're only using "ty" in your thank you page file names, and no other file names because then you'd get false triggers for your "Sign Up" goal. 

Now go setup a Regular Expression Google Analytics Goal!
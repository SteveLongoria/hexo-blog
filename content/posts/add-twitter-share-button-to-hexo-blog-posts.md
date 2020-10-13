---
title: How To Add A Twitter Share Button To Each Hexo Blog Post
date: 2019-02-08 19:07:48
tags: [Twitter, Share, Button, Hexo, Blog, Post]
---

So you want to add a Twitter Share Button at the bottom of each of your Hexo blog posts but you're not sure how to go about it. 

It's actually really easy and I'll show you how to do this really quick and easy in only a few minutes. This exactly what I did to add the Twitter Share Button you see at the bottom of this blog post in fact.

The first step is to [go here](https://publish.twitter.com/?buttonType=TweetButton&widget=Button) to get the code for your Twitter Share Button.

<center>![](/twittersharebuttoncode.png)</center>

Next, paste the following bit of code in the post.ejs file found in your Hexo theme layout folder. You can see exactly where to add it by viewing [my git commit here](https://github.com/SteveLongoria/hexo-blog/commit/b6b826adc92938b872bffe1eb94e25c2ef5adb1e) on Github.

```html
<a href="https://twitter.com/share?ref_src=twsrc%5Etfw" class="twitter-share-button" data-show-count="false">Tweet</a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>
```

Click save and that's it! You're ready to upload your new and improved Hexo theme!
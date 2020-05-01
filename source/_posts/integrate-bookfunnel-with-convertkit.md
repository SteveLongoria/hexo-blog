---
title: How To Properly Integrate Your BookFunnel Opt-in Landing Page With ConvertKit
date: 2020-05-01 13:45:32
tags: [bookfunnel, convertkit, integrations]
---

I helped out a client recently who was having trouble integrating his [BookFunnel][1] opt-in pages with his [ConvertKit][2] account. Not everyone opting in for his books on BookFunnel were being added to his ConvertKit account and he wasn't sure why. Some were being added but not everyone, which made it even more confusing to him.

He wanted everyone that opts in for his books to be added to ConvertKit so he can automatically follow-up up with them and announce new books he has to offer.

[BookFunnel does have documentation][3] walking you through how to integrate with popular email service providers (ESPs) but my client was still getting hung up on the integration. It wasn't working for him and if you're reading this it's probably not working right for you either.

**So how did I fix the issue?**

It was a simple fix actually, but one that can easily be overlooked. On the BookFunnel Integrations page under ConvertKit you'll see a notice in red:

![Bidding](/content/bookfunnelconvertkit-1.jpg)

![Bidding](/content/bookfunnelconvertkit-2.jpg)

This is why my client's funnel wasn't working properly. When visitors were opting in for his book, they were receiving a confirmation email from BOTH BookFunnel and ConvertKit. Some subscribers would confirm both of them, but not all of them would. This explained why some subscribers were being added to his ConvertKit list while others weren't.

To fix this, simply disable ConvertKit's confirmation email. In ConvertKit this is called the 'incentive email'. To disable it, simply edit your ConvertKit Form or Landing Page and make sure this box is unchecked:

![Bidding](/content/bookfunnelconvertkit-3.jpg)

That's it! Now every subscriber opting in via your BookFunnel page will be added to your ConvertKit account for further follow-up.

[1]: https://bookfunnel.com
[2]: https://convertkit.com
[3]: https://authors.bookfunnel.com/help/integrating-with-your-mailing-list-service/
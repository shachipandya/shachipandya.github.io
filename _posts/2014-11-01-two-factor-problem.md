---
layout: post
title: "2 Factor Authentication is Vulnerable Too"
external-url: http://blogs.hbr.org/2014/10/what-the-mission-to-mars-shows-about-indias-innovators/
---

So in the [last article](http://hardik.org/blog/two-factor-authentication/), I vouched about enabling 2FA on all your online accounts and services. Turns out, it's easy to game that as well.

Follow the link in the title and read about how the hackers gamed the 2FA via **cellular service provider** through call-forwarding and gained access to the auth-codes that were being sent through SMS on the victim's phone.

<div class="aside">However, this is not a failure of 2FA as a concept but it shows more of a problem in the method of using 2FA.</div>It's good to know that cell-providers can also play a part in the hack if the hackers really want something.

A quick-fix here is to **use an [Authenticator app](https://support.google.com/accounts/answer/1066447?hl=en) instead of SMS codes. At least there's one less possible point-of-failure involved.**

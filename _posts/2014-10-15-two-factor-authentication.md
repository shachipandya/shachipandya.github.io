---
layout: post
title: "2 Factor Authentication"
---

[Thousands of Dropbox passwords were leaked yesterday.](http://thenextweb.com/apps/2014/10/14/dropbox-passwords-leak-online-alleged-hack/) As always, PR people denied in an official press release but we all know better now. It's becoming a regularity lately. Consistently, one or the other popular online cloud-based service gets compromised and loses tons of passwords that are exposed openly.

**What's scary is the fact that Dropbox didn't notify me about the passwords being stolen.** It was 1Password and people on my Twitter timeline through which I came to know about this. It's always like this. The service doesn't notify users to change/update their passwords in order to save the name and protect the brand *(because it's embarrassing)* (with a happy exception of [Evernote](http://evernote.com) people who notified about such breaches back in the days when I used it). From the perspective of users, the behaviour of sweeping the outbreak under the carpet is unacceptable.

**First you had your service compromised so easily (your fault or not) and second, you don't even bother to let users know and suggest a password change.**

<div class="aside">More and more online services that hold vital user data/information are behaving irresponsibly towards the users.</div>

### What can we as users do?

We have to cover our tracks and protect ourselves. For quite some time now, I have made a practice and a habit to enable **2 Factor Authentication *or 2FA*.** It's a simple technique of cross-referencing and authenticating you as **you**. It's more secure than using the password alone.

## Here's how 2FA works

In a way, 2FA means adding 1 layer of security on top of the existing password layer. It combines **something you know (your password)** with **something you have (your phone)**.

So when you enter your password on an 2FA enabled website, it will ask your unique authentication code that only your authorised device can generate. Once you have authorised your phone to generate such codes, without the availability of these codes, it's not possible to access your account. So the thief has to know your password **and** have your phone physically with him to generate the unique code. This becomes less likely than just knowing/stealing your password from insecure connections or normal online hacking.

### Time-based One-Time Password (TOTP)

Now you may argue that this is akin to having 'another password that can be stolen'. Fret not, because it isn't. It combines a *moving layer of information* with your static hash to generate an OTP (One-Time Password) or the unique code. This moving bit of information is the **time counter.** Since time-based counter constantly changes, your code is unique every single time and hence it makes the system more secure than before. **This is why every new code you generate with the app has a limited time to live. After that, it becomes invalid and a new code is generated.**

<figure class="small">
	<img src="{{ site.url }}/images/tokens2.png">
	<figcaption>Sample token generated for a Dropbox login</figcaption>
</figure>

2FA is available on most of the famous online services like Gmail, Amazon Web Services, GitHub, Twitter, Facebook, Dropbox (ahem) etc. It's in your advantage to have it enabled and use it proactively to stay safe.

<div class="aside">2FA is nonintrusive, easy to use and fast. It's easy to grow as a habit for all your logins.</div>

Google has an Authenticator app that is capable of generating such codes and is pretty simple to setup with your favorite services. There's even Authy from [Authy.com](http://authy.com) for the Google paranoids like myself.

<figure class="minified"">
	<img src="{{ site.url }}/images/authyfinal.png">
	<figcaption>Authy.com is a great free 2FA token generator</figcaption>
</figure>

What you basically do is, download the Authy or Google Authenticator app on your phone and verify your phone number through an SMS/call. After that, you can scan unique barcodes from the respective web-services you use and upon scanning the barcode, the app on your phone becomes qualified to generate unique access codes to grant you access to your accounts online. **Your phone becomes your identity token with this app.**

### Caution

[This won't save you from all the apocalypse though.](https://news.ycombinator.com/item?id=7759332) On Internet, you are only as secure as the entropy of your passwords. Systems get broken and hacked all the time. Most of the times we get away with such attacks on a personal level because most people's information and data is not relevant and useful to the masse, unless you're [famous](http://en.wikipedia.org/wiki/2014_celebrity_photo_leaks).

### Does your favorite service support 2FA?

<div class="plaque-center">There's a way to check that. Here's an amazing website covering all your favorite services and a table of whether they support 2FA or not.
<a href="http://twofactorauth.org">www.twofactorauth.org</a>
</div>


### Some interesting reading on 2FA

So, while I researched more about 2FA, I found a couple of very interesting links that I think you should read. It explains the TOTP (Time-based One-Time Password) type authentication very clearly.

* [TOTP on Wikipedia](http://en.wikipedia.org/wiki/Time-based_One-time_Password_Algorithm)
* [TOTP in simple language](http://jacob.jkrall.net/totp/)

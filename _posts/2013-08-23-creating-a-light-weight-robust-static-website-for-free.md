---
layout: post
title: "Creating a light-weight robust static website, for free"
---

<em>**Update:** The website is now [hardikpandya.com](http://hardikpandya.com) and is built with Jekyll. It's running off of [Digital Ocean SSD Ubuntu server](http://digitalocean.com) after staying on GitHub Pages for a long time.</em>

---

My website [Hardik.co](http://hardik.co) was running on Squarespace till now. Squarespace is an all round platform that provides an efficient CMS, domain registration, templates, photography based portfolios, blogs and even [online stores](http://blog.squarespace.com/blog/squarespace-commerce-is-here) now. So I could do anything with it. When I started blogging back in 2007, I went with WordPress back then since it was easy to setup and was relatively cheap. Later on, it got boring and I came to know about Squarespace. Hardik.co was running on Squarespace for the last 1 year. But at all times, I was worried about my website and more than that, my content. Someday it could easily be the case when Squarespace (replace Squarespace with any proprietary lock-in you are stuck with) decided to pull the plug and all my content would be gone. **How can I be less worried about this? Only when I own and have the content in my control at all times.** So as my yearly ritual of freshening up the website backend, this time I decided to introduce a whole lot of changes.

First things first, I have no problems with Squarespace. It's an excellent platform for relatively uninformed (in terms of web) people to start websites quickly. But that is where the catch is - it's more for the uninformed and the non-fiddly kind. Which I have grown out of. For a long time now, I was feeling constrained by what Squarespace could do for me. Plus, no access of source files (like CSS and HTML) made it extra difficult to play around with the core of my website. This started becoming a problem. I wanted more control. When you talk about taking control of your web assets, you think of [Marco Arment](http://www.marco.org), [Paul Stamatiou](http://paulstamatiou.com) and other similar people who have gone static with their own websites. Call me paranoid, but companies on the web are there to make profits and not for charity. Trust is definitely an issue.

**So the stars aligned. I gave in. I went static. I went for freedom.**

I have [listed in past](http://hardik.co/blog/2013/make-a-website-for-free/) (okay, the title was cheesy!) why making such a static website would be a really nice option (for people like me who want to write and occasionally show off some photographs and do not really require heavy databases and SQL). 

I now know more than my own past self. So I can see more reasons why I should have gone this route (static site) much earlier. But anyway, I do so now. **This website officially runs on Jekyll (the Ruby based blogging system) and is hosted on an Amazon S3 bucket somewhere in Ireland (I like to be in the center of the world, at least geographically).**

Now yes, I tested the website design and everything on [GitHub Pages](http://pages.github.com/) because well, it's free. You can host your static website on GitHub Pages for as long as you want without paying a dime. But there's a catch: **source code of your website will be openly visible to everyone** and anyone can fork it for their use. You can only secure source code of the website on GitHub by paying $7 a month for their basic plan that includes 5 private repositories. I do not want to do this. Because one of the reasons of moving away from Squarespace is their $8 a month price point. I don't mind paying for the site (I did it happily for all these years) but for what I want to achieve with my website (share static articles and pictures), it does not make sense to pay for a server. At the same time, I want to secure my source too. So GitHub is not an option for final deployment (although it's very easy to get started on it while testing and playing with Jekyll).

On enough fiddling, I decided to go with **Amazon S3** for a number of reasons: 

- I could secure the source of my website.
- Traffic handling capacity of my website is scalable now. So if someday suddenly something went viral from this website (highly unlikely if you ask me), I can rest assured that my website will handle the traffic, thanks to AWS. This makes it a very robust option.
- Almost zero operational costs. The pricing structure of S3 is very generous if you ask me. If your website is small with decent traffic, you will almost always end up saving money (yes I know GitHub Pages is completely free).
- [I have met Werner Vogels (the CTO of Amazon)](http://hardik.co/blog/2013/Google-Glass-experience/) and he is an awesome inspiration. His own website is static and runs off of S3. So I like to follow in his footsteps.
- **I love Amazon.** They are one of those companies that don't give a crap about tracking you and creeping you out by being weird because well, it's not their business model. You pay (for what you use) and they give you what you want. Also, Amazon Web Services (AWS) is something you want to learn and use anyway.

So S3 (secure storage service) allows you to host a static website on your AWS account. There are plenty of very good tutorials already written about the process ([here](http://jonknapp.com/2013/01/deploying-jekyll-to-s3/), [here](http://www.savjee.be/2013/02/howto-host-jekyll-blog-on-amazon-s3/) and [here](http://www.allthingsdistributed.com/2011/08/Jekyll-amazon-s3.html)) so I will not add to that list. Those links I mentioned already assume you have a Jekyll blog. But I believe you might not already have one, so go [here](http://jekyllrb.com/) to see how to make one on Jekyll.

### What if you don't like Amazon S3?
Well, you could go with GitHub Pages. If not that, try [BitBucket](http://bitbucket.org)'s static website hosting service. They do not support Jekyll compiling on their own so you will have to upload your *_site* folder that you get after compiling your site locally. I would also suggest [NearlyFreeSpeech](http://nearlyfreespeech.net) for hosting your site. They have a 'pay for what you use' model. Since your website is (likely to be) lean and light-weight, hosting possibilities are endless. Choose what you like.

### How do you maintain version control?
It's important to maintain a track record of changes you make to your site. At least it's worth looking at when some changes do not go as planned. If you host your site at GitHub Pages, you get the version control from GitHub so that is not a problem. Amazon S3 or most other static hosts do not provide a version control. I use BitBucket for this. BitBucket is a distant cousin of GitHub with a nice feature: __private repo for free__. Job done for me!

### Advantages? There are plenty
- **The website loads insanely fast now** (at least compared to its old loading speeds). This is very important in the current days of mobile computing. Try opening this site on a mobile device or a tablet (it's also responsive).
- **I control everything now - the design, URL schemes, number of pages (Squarespace has a limit on this), layout and total size of the website.** This level of control is not possible with proprietary CMSs and lock-ins.
- I own the source code. This adds to the previous point. This is not allowed in most CMSs. 

There are maybe more advantages but these 3 were enough for me personally to make that transition. 

### Why not WordPress? (some might ask)
Yes it's open source and it's the pillar on which many popular websites stand today. But again, I don't require a PHP based database backend and complex setup for my blog. It's redundant and it takes a lot of time to manage. It often involves dealing with updates of software and updates of plugins as well. Plus, playing around with themes is a very complex task (well, at least for me). So this is a no.

### Are there other static platforms available?
Yes oh yes! There is a bunch of them. Personally I would try out [Kirby](http://getkirby.com) someday. There is also [Stacey](http://staceyapp.com/), [Second Crack](http://www.marco.org/secondcrack) and [Octopress](http://octopress.org/).

### Are there any apps for publishing static sites?
Not specifically. But there can be a workflow setup for such a purpose. For OS X, you could use [Hazel](http://www.noodlesoft.com/hazel.php) to **look** at a certain folder in Dropbox and transfer your drafts or blogposts to your local repository (in case of GitHub Pages as your host) or to a local folder on your laptop that has your website. Then to compile your website with Jekyll and syncing/uploading it to the server, you could schedule a script through [Lingon](http://www.peterborgapps.com/lingon/) to run at certain times of the day. When the script runs, your changes (i.e. new blogpost) will be pushed to your website. Due to the static nature, the post instantaneously goes live of course. 

### Are static websites really that popular?
Yes. There's a whole cult of people who have recently gone static and more and more people make the switch everyday. [Here's a list](https://github.com/mojombo/jekyll/wiki/sites) if you want to see. Famous people like Harry Roberts (the [CSS Wizardry](http://csswizardy.com) guy) have their websites running on GitHub Pages. So there is no reason for you to not go with it.

### But do these static websites look nice and modern? Here are some themes you might want to start out with
Of course! When I was considering the switch, I was looking for nice designs (themes) for Jekyll. When I found the ones I liked, I bookmarked them for my reference. I share some of them here. Use them as a starting point for your adventure. But hey, if you want to fork the source of any one of these sites, do ask for permission of its respective owner or check the licenses underneath its source on GitHub (most people are nice and won't say no). To get to the sources of these sites, just search (Ctrl+F is your friend) their names on [this page](https://github.com/mojombo/jekyll/wiki/sites).

- [Jeremy Thomas's site](http://jgthms.com/)
- [Dan Loewenherz's site](http://dlo.me/)
- [Dan Kim's site](http://dankim.org/)
- [Nathan Staine's site](http://nathanstaines.com/)
- [Kasper Mikiewicz's site](http://idered.pl/)
- [Andrew Wolfe's site](http://awolfe76.github.io/)

For me, this is my website now. This is my playground to test, experiment and break stuff. It has the same domain, the old links will obviously still work (see the difference? had I moved to a proprietary CMS, they might have disallowed me to keep the same URL structure. But in Jekyll, I'm the boss and I configure stuff the way I like). I personally had good help from Cole Townsend ([@CTRunsThis](http://twitter.com/ctrunsthis)) for design, so a hat tip for him. The fonts served are from [Typekit](http://typekit.com) and can easily be from anywhere else as and when I please (see? that is freedom!). The design and source code of Hardik.co is private but I see no harm in sharing it with you if you promise not to copy it blatantly. 

### A word of caution on exporting files
I realised this later but I felt it was worth noting. While trying to export posts from Squarespace, the process went all haywire. I have an _.xml_ file from Squarespace that I am supposed to import in to WordPress. __Yes, Squarespace exports are only compatible (by default) to WordPress format.__ But dear Squarespace, what if I want to have my posts in simple markdown format? Nope, to even expect that is crazy I guess (stupid lock-ins). This has just made me love my decision of taking control even more. For now, I'm slowly moving all old posts here (important ones transferred first of course) and some posts might not make the cut. This is just too painful to do and I never ever want to go through this again.  

But hey, if you really dig this design and would want to try it for fiddling and inspiration here you go: mail@hardikpandya.com.
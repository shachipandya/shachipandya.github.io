---
layout: post
title: "Flaw in the Reporter-style data"
---

It's advisable that you read the [previous article](http://hardik.co/2014/03/15/acquiring-data-about-life/) to better understand what I am going to explain here.

<figure class="minified">
	<img src="{{ site.url }}/images/reporter.png">
	<figcaption>The Reporter app</figcaption>
</figure>

I discussed in the last article how [Reporter app](http://reporter-app.com) provides a means of gathering information about your daily life and activities. The data however is not accurate and representative of your routine. The problem lies in the methodology of the data-acquisition.

The app asks you questions about what you are doing, where you are, with who you are and pretty much anything you configured it to ask you about (this itself is a hack since you cannot create a statistically complete set of questions to quantify all the aspects of your life).

### The issue with data nonlinearity

Furthermore, the problem arises even after you have set a few questions. The app reminds you to enter data (*reports* as they call it) by push notifications. When I'm busy, I defer entering that data to a later time. This clusters up data-points non-linearly and creates a distorted measurement of your day.

Check the image below.
<figure class="minified">
	<img src="{{ site.url }}/images/reporterdata.jpg">
	<figcaption>Nonlinearity in measurements</figcaption>
</figure>

As you can see, in the first case, you ideally report data at the time you are notified to enter it. That creates data-points that are evenly spaced out in time creating a uniformity. But the problem arises when you defer entering data (resulting in the case of *stretched data* as shown in the image) to a later time which creates nonlinearity (excuse my handwriting which got distorted due to the crippled table in the cafe).

> Nonlinearity = less data about the times when you are busy and more data about the times when you are free

Ideal? Not really. But the app is cool nonetheless. 

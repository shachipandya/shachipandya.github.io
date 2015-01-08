---
layout: post
title: "Rewriting the Bonescript for BeagleBone"
---

So this has been a code-heavy week for us at [Octal](http://theoctal.com).

<figure class="minified">
	<img src="/images/bbblack.jpg" width="50%" height="50%">
	<figcaption></figcaption>
</figure>

We have been working on controlling physical objects with the very capable BeagleBone Black. There's a JavaScript library written for the BeagleBoard named [bonescript](https://github.com/jadonk/bonescript) by [Jason Kridner](http://twitter.com/jadon). That is what we are using from the beginning for our purpose. We want to control outputs with inputs given through a software interface. The outputs need to be controlled by the BeagleBone. We needed GPIO pins for those outputs. The BeagleBone Black has 65 GPIO pins on it in total. For our purpose, we needed at least 54.

Unfortunately, setting up GPIO pins as outputs is not as simple as on the Arduino. BeagleBone requires a bit of trickery to have those GPIO pins properly ready and available. Initially as my fellow programmer Aditya describes [here](http://aditya.patadia.org/2014/05/octalbonescript.html), defining GPIO pins as output pins with the `setPinmode` function kept throwing errors. Some of the pins were failing to be configured as output. That left us with less than 54 pins for use as GPIO.

### The HDMI cape problem

We discovered that there's a pool of pins that are used for the HDMI port on the board. Those pins cannot be reconfigured without disabling the HDMI cape ([as shown here](http://elinux.org/Beagleboard:Weather_Cape_Work-Around)). So there's that with those pins. It's rather trivial to make those pins available even though it's very unintuitive. **Here's the tip: open the** `uEnv.txt` **file on the root of your board and uncomment the HDMI cape line. Then reboot the board, and you have those HDMI pins available straightaway.**

Moving on. We needed even more. After spending more than 10 nights on this, we found out that the existing [bonescript](https://github.com/jadonk/bonescript) code had a few issues which prevented us from setting those pins and was also bringing in a slew of problems in the efficient execution of the code. We decided to take matters in our own hands - forked the repo and started working on it.

A range of improvements followed in the original bonescript code. Overall, Aditya did a lot of work on the JavaScript source code and made it better in many ways ([read all the improvements on his original article](http://aditya.patadia.org/2014/05/octalbonescript.html)). And finally, we decided to release the rewritten bonescript as our own improved release.

With this new OctalBonescript, you can have all possible GPIO pins at your disposal barring the eMMC pins which are not possible to be used as GPIO. **The unusable pins are 3 to 6 and 20 to 25 on P8.** Effectively, we can have 65 - 10 = 55 pins. Just works for us!

## Final pin diagram for your reference

<figure class="minified">
	<img src="{{ site.url }}/images/bbbpins.jpg">
	<figcaption></figcaption>
</figure>


## Brand new Octalbonescript

Get it here: [theoctal/octalbonescript](https://github.com/theoctal/octalbonescript)

It works and has been tested on BeagleBone Black Rev B and Rev C. It installs [socket.io](http://socket.io) and [Express.js](http://expressjs.com) as dependencies. It's also Mac OS X ready for your testing when you don't have the BeagleBone with you.

To install it as a Node.js package: `npm install octalbonescript`.

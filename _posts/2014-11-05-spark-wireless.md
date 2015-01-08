---
layout: post
title: "Spark Core"
subtitle: "The networked controller built for the IoT age"
---

For the uninitiated, [Spark Core](http://spark.io) is a wifi-enabled programmable microcontroller board and the first of its kind that comes pre-compatible with web-connectivity and a JavaScript programmability through a library core. It's equipped with 8 digital IO and 8 analog IO pins.

We at Octal, ordered 2 of them for a couple of upcoming projects and research. It was quite a chore to get them through the Indian customs since being equipped with **wireless chip antennas** is something that raises all kinds of suspicions. I managed to get the boards in my hands after a month-long quibble. If you're ordering them, make a note to get them sent through a courier service (e.g. DHL, FedEx) instead of the postal route.

## The board

<figure class="normalised">
<a href="{{ site.url }}/images/sparkio.png"
   class="fresco"
   data-fresco-caption="Spark Core connected to computer via USB"><img src="{{ site.url }}/images/sparkio.png"></a>
<figcaption>Spark Core connected to computer via USB</figcaption>
</figure>

This is a simple Spark Core device with **8 digital and 8 analog pins.** Pretty simple stuff so far. The chip on the top you see is a wifi antenna that gives it a capability to connect to the network. That's the best part. These are networked IOs and can be governed via physically distant switches/controls.

So I connected the Spark Core with the USB and downloaded the Spark Core app on the iPhone. It took about 2 minutes to configure the iOS app over the wifi network and it immediately identified the Spark Core that was waiting on the network. Voila!

## Controlling IOs wirelessly

It happened. Check the images below.

<ul class="rig columns-2">
	<li>
<figure>
<a href="{{ site.url }}/images/spark-ios.png"
	class="fresco" data-fresco-group="one"
	data-fresco-caption="Turning on the D7 pin with a tap on the Spark Core app..."><img src="{{ site.url }}/images/spark-ios.png"></a>
<figcaption>Turning on the D7 pin with a tap on the Spark Core app...</figcaption>
</figure>
	</li>
	<li>
<figure>
<a href="{{ site.url }}/images/spark-on-annotated.png"
	class="fresco" data-fresco-group="one"
	data-fresco-caption="...and seeing the D7 LED turn on in near real-time"><img src="{{ site.url }}/images/spark-on-annotated.png"></a>
<figcaption>...and seeing the D7 LED turn on in near real-time</figcaption>
</figure>
	</li>
</ul>

Nerdgasm anyone? This is really game-changing. Mind you, there's no connection between the phone and the chip apart from the wifi layer and the transmission of the signals happens through the [Spark Cloud API](http://docs.spark.io/api/) with proper authorization. Spark Core controller can be operated wirelessly meaning that you have your Input/Output pins accessible from **Anywhere (with a capital A).**

>I know you could do this with an [Arduino](http://arduino.cc) and a wifi-shield and nearly any other networked microcontroller, **but the ease and simplicity that Spark Core provides is above everything.**

There's barely any setup required and you are good to go in no time.

The app is however rather limited in functionality in that you can at most flick the digital pins high and low and play around a bit with the analog pins, but nothing more than that. Anything fancy and you will have to design your custom code and upload it on the Spark Core.

And Spark Core is taking a huge leap in that direction by putting a cheap and easy-to-use controller in people's hands. I am a big proponent of simple systems that just work out-of-the-box and Spark Core hits the spot perfectly.<div class="aside">The future is networked interfaces.</div>

I cannot wait to build things with this. Uploading custom codes is the next frontier. I will share more soon.

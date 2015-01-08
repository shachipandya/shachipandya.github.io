---
layout: post
title: "Octalbonescript for BeagleBone"
---

<div class="aside">Octalbonescript really is the most stable and powerful library to control and program your BeagleBone.</div>

The thing with embedded electronic platforms such as [Arduino](http://arduino.cc), [BeagleBone](http://beagleboard.org), [PandaBoard](http://pandaboard.org), [Intel's Galileo](http://arduino.cc/en/ArduinoCertified/IntelGalileo) and the [Raspberry Pi](http://www.raspberrypi.org) is that they are all at a higher (abstraction) level, the same - they all have processors, GPUs (in most cases), clocks and are capable of handling digital and analog inputs/outputs. The difference lies in the way they are programmed, the way their internal software architecture is laid out at the lower level. **The usefulness and versatility of a platform is determined by the software.**

BeagleBone is a very advanced hardware platform. It's capable of running modern Linux distributions very ably. We use <span class="highlight">Debian</span> on it and you are free to choose your favorite one you like. **Where we make a difference and excel is the way we use JavaScript to make the programming of GPIO (General Purpose Input Output) pins and on-the-fly definition of them easy, reliable and fast.**

### Our main aim for Octalbonescript

  1. Defining Digital Input Output
  2. Defining Analog Input Output
  3. Defining Pins to act as either Digital or Analog

In controlling electronics using software, these are the essential functions we use. And having a flawless execution of them with an existing robust library is a non-trivial advantage to have.

## Where Octalbonescript shines

* **All I/O operations and function calls are fully asynchronous** which is the best (and most powerful) mode of program operation (we stand by that with real-world applications and testing experience).
* The Watchdog Timer is implemented for automatic reboot when system becomes unresponsive.
* Universal cape is now used by default which helps to remove almost all the errors related to `pinmux` and makes `setPinmode` function very fast.
* If HDMI cape is disabled (you can do that from the `uEnv.txt` file on your BeagleBone), the **dedicated HDMI pins can also be used as GPIO and we load the cape for it automatically.**
* Intuitive names for files and functions: no more `my.js` and `myrequire()` functions (there's no 'i' in team, right?).
* Brand new **Simulator Mode** for OS X and Linux - for your local testing of code for errors.
* Better **Debug Mode** - now debug statements are printed only when `DEBUG=bone` is passed while execution of your code.
* Finally, the library is much more reliable, throws intuitive errors if ever they occur.
* We actively test the library and promptly respond to issues and questions.

<div class="box"><strong>No offence to the creator, but the original bonescript was (and mostly still is) a mess.</strong> It's less frequently updated if ever, and almost never tested. We don't like it even though our whole work for Octalbonescript was based off of it. We spent nights and days on fixing the code and we think we have created something far better, progressive and futuristic.</div>

We'd be glad if you tried it. Get the source and hack on it. Raise an issue on Github if you are stuck.

[Here's the Octalbonescript source-code.](https://github.com/theoctal/octalbonescript)

Install it as a Node package: `npm install -g octalbonescript`.

We also have a shiny website: [octalbonejs.com](http://octalbonejs.com).

For bugs, issues and questions, we're always listening: [@hvpandya](http://twitter.com/hvpandya), [@adityapatadia](http://twitter.com/adityapatadia), [hardik@hardik.org](mailto:hardik@hardik.org).

***

<center><h3>A little back story</h3></center>

When we started working on BeagleBone last year, there really was not a lot available. By that I mean there was too little material and literature to start with. We had ventured into a completely unknown territory for us. <strong>We knew the Arduino in and out, but it was lacking a fundamental functionality we required - a good solid client-server style web application capability.</strong> In this day of web and Internet and interconnectivity, having the ability to run software over the cloud is essential. It's the future after all. So just out of curiosity and the want of a better (web-capable) platform to develop on, we had looked in to the BeagleBone and had started playing with it.

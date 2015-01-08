---
layout: post
title: "LiveNote is open source"
---

This was the plan. We were just not sure about the timeline. But now it's clear. We have opened up LiveNote source for everyone interested.

This is where you can get it from: [theoctal/livenote](https://github.com/theoctal/livenote)

### Here's what you need to know for now

1. The `app.js` is the application file. It's the code of the main app. You can tweak various parameters there and build a custom LiveNote for yourself.
2. The `index.html` is the front page of the website [www.livenote.org](http://livenote.org).
3. The `app.js` already supports creation of random URLs as the IDs of your notes.
4. LiveNote currently does not use `https`. But that shouldn't stop you from trying it out on your own version.
5. The notes can be accessed if someone tries to guess the note ID and successfully manages to do so. Hence, randomization of note IDs is preferred and is controllable by code.
6. We shipped LiveNote without a signup and login. That was intentional to keep it simple and fast.
7. It's built with Websockets library [socket.io](http://socket.io), which enables it to be fast.

To host your own LiveNote clone, you will need to have a few packages installed on your server.

### List of required packages

* [Node.js](http://nodejs.org/): the main server application
* [Express.js](http://expressjs.com/): the framework for node.js
* [socket.io](http://socket.io): for catching events and firing database updates
* [SQLite](http://www.sqlite.org/): for storing the database of created notes
* [jQuery](http://jquery.com): for client-side data handling
* [Bootstrap](http://getbootstrap.com/): for client-side styling

In case you need help with setting it up, mail us at [mail@theoctal.com](mailto:mail@theoctal.com). For quicker response, use Twitter [@OctalHQ](http://twitter.com/octalhq).

I plan to publish a detailed tutorial of *how we built it and how it works* later on.

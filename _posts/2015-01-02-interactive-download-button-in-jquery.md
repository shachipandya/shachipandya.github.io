---
layout: post
title: "Interactive Download Button in jQuery"
subtitle: "A download button that does more than sitting dead"
---

As I shared in the [previous article](http://hardik.org/blog/fifth-gear-coding/), I have recently completed a bit of work on [jQuery](http://jquery.com) and I'm fiddling around with a few examples and UI components.

I recently had a couple of Download buttons in my article that were basically just links to file on server. I thought I should make them a bit more interactive rather than just dead links. So I added a bit of jQuery and made them informative.
This is just start and a lot can be done with some more scripting but here's the first iteration.

<pre class="language-javascript" rel="css"><code class="language-javascript" rel="css">
var $button = $("a.download-button"); //finding the matching buttons on the DOM

$button.on('click', function(){  // adding click event handler to the buttons
  var $clickedButton = $(this);  // storing the current button for reference
  var $href = $(this).attr("href");

  $clickedButton.text("Downloading...");
  $clickedButton.css("background-color", "#275AB0");

  setTimeout(function(){
    $clickedButton.removeAttr("href"); // remove href so further clicks don't trigger download
    }, 50);

  setTimeout(function(){
    $clickedButton.text("Downloaded.");
    $clickedButton.css("background-color", "#aaa");
    }, 1500); // this executes 1.5 seconds after click event

    $clickedButton.off(); // remove the event listener to disable further clicks

});

</code></pre>

<div class="jsbin">
<a class="jsbin-embed" href="http://jsbin.com/xowiha/17/embed?output&height=300px">Interactive Download Button in jQuery</a><script src="http://static.jsbin.com/js/embed.js"></script>
</div>

<div class="disclaimer">Also, <a href="http://jsbin.com">JS Bin</a> is awesome and you should totally use it.</div>

As you can see in the code block, I've put a <u>small delay (50ms) before removing the</u> `href` <u>attribute from the link</u> because if I remove it instantly, the resource (file) cannot be reached when the user clicks the button, so the downloading doesn't happen. Any small amount of delay can be used.

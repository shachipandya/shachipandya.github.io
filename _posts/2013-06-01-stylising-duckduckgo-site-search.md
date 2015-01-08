---
layout: post
title: "Styling DuckDuckGo site-search"
---

So this one came from a problem I was having myself. I had the default Squarespace search setup for my website but I wasn't happy with it. Its behaviour is something absolutely naive considering the fact that it blanks out the screen every time you tap in the Search field and start typing something. That is also a 'giveaway' that your site is Squarespace-powered. I wanted to change that.

So I turned to DuckDuckGo for my website's custom search. [This is the page](https://duckduckgo.com/search_box) you should visit to set it up as a simple iframe element on your website. But for me, it was not perfect because I hated that green button. I wanted a clean and blank search-box with no extra glitz.

So I used an HTML form and customised it by adding the necessary ones from the URL parameters DuckDuckGo offers [on this page](https://duckduckgo.com/params).

{% gist hardikpandya/5692558 %}

It passes the URL parameters that are mentioned above as inputs. Each parameter helps modify the behaviour of the resulting search page that will open in a certain way (e.g. link colours, link fonts, background colour and more). Modifications can be in any amount and any number. You can add or remove lines from the code snippet above. Place the code snippet in an appropriate div tag on your HTML page where you want the search-box to appear.

Furthermore, I styled it (with CSS) with the help of existing search-boxes implemented on a lot of other websites. Since the search-box is identified in the HTML with 'search' tag, the CSS is written accordingly.

{% gist hardikpandya/5692566 %}

Everything in the above CSS is how I wanted it, including the dark shadow around the search-box in the 'focus' mode. You can alter everything and make it match the design of your existing blog or website.

### Comparing the search windows

<figure class="small">
	<img src="{{ site.url }}/images/searchold.jpg">
	<figcaption>Default DuckDuckGo search box</figcaption>
</figure>
<figure class="small">
	<img src="{{ site.url }}/images/searchnew.jpg">
	<figcaption>Styled DuckDuckGo search box</figcaption>
</figure>

I found this worth the effort because the end-result exactly matched the colour scheme of my website. Plus it now looks much more generic and standard.

Folks at DuckDuckGo appreciated this and [wrote about it too](https://twitter.com/duckduckgo/statuses/340932514354966529).

+++
title = "Html and CSS"
date = 2025-10-19
+++

This is myself writing after wrapping up a second days work on this website, here's a log of what I've added...

Containers! I have now figured out a good system for the home page with three containers I can easily slot in extra sidebars 
wherever I need. I believe the sizing *should* work with most screen sizes, but it's probably best if you're reading this on a desktop.
+++

**The Base.html**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>nathangerryts</title>
    <link rel="stylesheet" href="/css/style.css">
  </head>
  <body style="background:url('/gifs/stars4.gif');">
    <div class="container"> 
      {% block content %} {% endblock content %}
    </div>
  </body>
</html>
```
If everything worked properly then that code block above should also be syntax highlighted. I'm currently using Zola as my static site generator. You can find the source code [here](https://github.com/Nathongols/nathangerryts.github.io)

Zola uses the Tera templating engine, which is similar to other template syntax like Jinja2 and Django. You can see in the base that we define the body of the page (all page content) and create a content block that we can reference in any file we inherit.

**The Index.md**
```html
{% extends "base.html" %}
{% block content %}
<div class="container"> 
  <marquee direction="left," scrollamount="20">WARNING!!!! THIS PAGE IS UNDER CONSTRUCTION, BROWSE AT YOUR OWN RISK!!</marquee>
  <header></header>
  <main>
    <div class="left-container"></div>
    <div class="center-container"></div>
    <div class="right-container"></div>
  </main>
  <footer align="center"></footer>
</div>
{% endblock content %}
```
These three divisions are how I divied up my page content for now, the center-container class handles my main page content across the site, with the left and right containers to add additional content if needed. 
currently there exists one class for sidebar content (called sidebar) but I plan to create a number of different template classes to mix and match at will.

**The Style.css**
```css
.center-container {
  background-color:black;
  border-image-source: url('/pngs/MSDOS-header-border.png');
  border-image-slice: 28 56 6 56;
  border-image-repeat: round;
  border-style: solid;
  border-width: 28px 56px 6px 56px;
  image-rendering: pixelated;
  color:#FFFFFF;
  padding: 0px 20px 20px 20px;
  width: 100%;
  height:auto;
}
  
```
Style! much of todays was spent configuring my base style.css, big props to solaria for an amazing [guide](https://solaria.neocities.org/guides/borderimage/) to border images in css, (and the lace borders <3).
Took a little bit, but I managed to create the MSDOS window border that you're seeing this post in right now! 

The foundation has now been set so I have a pretty good system to continue pushes content to this page. Keep an eye out!



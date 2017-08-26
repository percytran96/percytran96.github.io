---
layout: post
title:  "Project: Pan and Tilt"
date:   2015-10-05 17:31:46 -0400
categories: blog
---

### Introduction
The purpose of this project was to understand and closely examine the device orientation capabilities with respect to its software.

### Methods and Resources
A basic program was provided that showed the working of device orientation using its hardware like gyroscope. 
These properties can be used to build interactive web apps. To demonstrate we used two different shapes: a 
square as center and a circle as ball.


After creating simple HTML and CSS files, I changed the provided JavaScript code to make the page interactive using device orientation API. The device orientation event returns only the rotation data, which includes how much the device is leaning front-to-back (beta), side-to-side (gamma) and if the phone or laptop has a compass, the direction the device is facing (alpha). The program first checks for compatibility. If it’s compatible then it listens and handles the event.

{% highlight javascript %}
window.addEventListener("deviceorientation", orientationCallback, true);
{% endhighlight %}

The following JavaScript code was used to mirror the effect in HTML.

{% highlight javascript %}
function init() {
  if(window.DeviceOrientationEvent) {
    document.getElementById("text").innerHTML = "Supports orientation events";
    window.addEventListener("deviceorientation", orientationCallback, true);
  } else {
    document.getElementById("text").innerHMTL = "No orientation event support";
  }
}

function orientationCallback(eventData) {
  
  var tilt = eventData.gamma;
  var pitch = eventData.beta;
  document.getElementById("text").innerHMTL = eventData.gamma + " " + eventData.beta;
  if(pitch  90)
    pitch = 90;

  if(tilt  90)
    tilt = 90;

  var d = document.getElementById("center");
  var x0 = (window.innerWidth - d.offsetWidth) / 2;
  var y0 = (window.innerHeight - d.offsetHeight) / 2;

  d.style.top = y0;
  d.style.left = x0;

  var c = document.getElementById("ball");
  var x = (window.innerWidth - d.offsetWidth) / 2;
  var y = (window.innerHeight - d.offsetHeight) / 2;

  var dx = x * tilt / 90;
  var dy = x * pitch / 90;

  c.style.top = y + dy;
  c.style.left = x + dx;
}



alert("javascript loaded");
window.onload = init;
{% endhighlight %}

### Results
The [video](https://youtu.be/sNqzuCuD5yg) shows the results where we can see the square box in the center with the ball hovering over it. The position of the ball can be changed using device pan and tilt. When you load the page and move the device around, you should see the position of ball change as the device moves through space and is affected by acceleration.
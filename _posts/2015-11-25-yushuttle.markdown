---
layout: post
title:  "Project: YU Shuttle"
date:   2015-11-25 22:15:09 -0400
categories: blog
---

York University, Canada's third largest university has a shuttle service for it's students at Keele Campus.
Students can ride the shuttle to residences nearby, GOTrain Station, other university campuses for free. 
All the shuttles have a fixed schedule for all their stops and all the drivers are very punctual so it is
very rare that it gets late.

### Problem
I was a regular user of Transit App to track TTC buses before moving to campus. Since I moved to campus 
I started using the shuttle however it was a pain in the ass to track it's schedule. I would often miss the shuttle
by a few minutes and the next one would depart in half an hour or more. It was all a waste of time. 


After some digging I found the shuttle schedule on the university's website. This website is not mobile 
friendly, difficult to use and hardly interactive. Not only that, the website becomes unresponsive on smartphones.


It was hell.

### Solution
The idea was simple - create a webapp that shows how much time is left untill the next shuttle's departure and when.
However the implemetation was challenging because of serveral reasons:

1. Irregular and inconsistent gaps between departures from university
2. Diffrent schedules for shuttles and days (weekdays and weekends)

Using the schedule from the website I created a function with different cases for times in plain JavaScript that would
run client-side. By using a recursive pattern I was able to solve the problem in a precise manner. I used a simple
HTML5 responsive boiler plate to show the calculations. 

### Future
Soon dozens of people started using my app and it gained popularity within a few weeks. I presented this app at
YU HackFest as well where it recieved high praise.

Right now the app shows schedule only for Village (nearby student residences) but I am planning to scale my app
to cover all the shuttles.

### Contributing
If you're interested, please fork the repository, make changes and submit pull request.


{% include icon-github.html username="aamirsahmad" %} /
[yorku-shuttle-webapp](https://github.com/aamirsahmad/yorku-shuttle-webapp)

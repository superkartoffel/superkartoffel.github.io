---
layout: post
title: "WebDoko: first milestone"
date: 2019-04-27
tags: webdoko
---

The first milestone of the [WebDoko project](/projects/webdoko) has been reached:

## Offline Doppelkopf game for mobile and desktop.

[Try out the online demo.](https://vorwerk.me/webdoko/)

My goal was to learn something by implementing a Doppelkopf game using web technologies. Did I succeed? 

I think so. I learned:
* how react works and how to write a simple web application with it
* how to deal with git
* how to set up an automatic build process with gitlab
* how to write a progressive web application that works offline

Which of my original goals didn't I achieve?
* "responsive design techniques, probably material design"

While the game works both on the phone and on the desktop, it has not been optimized for responsiveness to different screen sizes. It merely works because the user interface is so simple.

All in all, the user interface is not elaborated. Basically, there are a number of buttons that can be faded in and out as needed.

Also there are still a lot of features missing. For example:
* You cannot restart a game round.
* Compulsory solos are not enforced at the end of the round.
* The vector graphics load very slowly on Android phones for some unknown reason.

If this was going to be a production grade game, it would generally need a lot of polishing.

But since the goal of this project is to learn new things, I won't do that and continue with the next milestone instead. I'm still not sure which one it will be, and I have to be careful not to start several at once. But I've already looked at some WebRTC solutions and [Janos](https://janus.conf.meetecho.com/) looks like it's an easy choice. So stay tuned.

You can find the source code in the [gitlab respository](https://gitlab.com/superkartoffel/webdoko).

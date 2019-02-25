---
layout: post
title: "WebDoko project announcement"
date: 2019-02-25
tags: webdoko
---
One of my favorite card games is [Doppelkopf](https://en.wikipedia.org/wiki/Doppelkopf). I have previously implemented 
an online version of this game using Unity3D, but this project was retired right before it was released to the public.

I'm going to try again now. But this time everything will be different of course. My main goal for the project is not 
the implementation of the game itself, but to learn new skills in the process. Therefore I will target some very different 
topics.

Here are my main milestones:

## Offline Doppelkopf game for mobile and desktop.
That should be relatively easy to achieve, considering I've done it before. You will be able to play against computer 
players according to [DDV rules](https://doko-verband.de). The computer players will not be very smart at this point. 
In order to achieve convergence between mobile and desktop, I will go for a web-based implementation.

Stuff I expect to learn in this step:
* Javascript
* Progressive Web Applications
* modern Javascript front-end frameworks, probably [react](https://reactjs.org/)
* responsive design techniques, probably material design
* user interface design libraries

## Online Doppelkopf game with audio communication
Playing against the computer is not much fun, especially if there is not an advanced logic behind the implementation of 
the opponents. There are two solutions to that: either find some friends and play against them, or make the computer 
smarter. Therefore, one could reverse the order of this and the next milestone. 

To play against other human players you would at least need a basic network communication interface. I want to go one 
step further and also let the players communicate with each others too. Text messages feel too cumbersome, especially 
on mobile devices. Video presence is unnecessary and too demanding in terms of network bandwidth.
Therefore my compromise is audio communication. The feature should work seamlessly, ideally without any user interaction 
necessary.

Since this project is still web-based, the go-to technique here is called WebRTC. 
I will probably need another communication scheme for the actual gameplay.

## Smart bots 
Developing a good Doppelkopf computer player based on rules is not easy, because this game is also about players playing 
in teams with (hopefully) coordinated strategies. I will use this challenge to learn how to train an artificial intelligence 
capable of working with human players in a team.

## AR interaction 
Sitting at your desk using a computer mouse or some touch interface is fine when you are alone in your room. But if you 
want to play Doppelkopf with others in the same room you would want to use actual playing cards. Mixing both situations, 
i.e. playing with some friends in the same room and some connected via the Internet, is the task for this milestone. A 
simple approach would be to stream a video of the tabletop to the remote player, and have a projector that virtually shows 
all the cards played by the remote user.

So this milestone will involve some additional hardware and will probably not even be based on the code written in previous
milestones.

# Afterthoughts
I'll probably get into trouble because I don't incorporate all the planned features into the design in advance. For example, 
to design the game in offline single player mode first and then switch to online multiplayer mode later. But, as I said, 
the main goal of this project is not to get a perfectly finished product in the fastest possible way. It's more about 
learning new things. And I can only do that if I work on one topic at a time. I have no problem throwing away most of the 
code after each milestone.

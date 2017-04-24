---
layout: post
title: "Accelerated view synthesis"
date: 2012-01-31
---
In this post I want to introduce you to the topic of my bachelor thesis. I will try not to go too much into detail and try to describe it in a way everybody can understand it.

>Accelerated Implementation of a View Synthesis Algorithm for 3D Video Sequences

The title sounds complicated, as it should be for a scientific work. So what is it about:

# View-Synthesis
![view-synthesis](/images/view-synth.gif)

View-synthesis means that in a video sequence the camera position is changed afterwards and thus the observed scene can be shown from a different angle. What's the point? Legitimate question. In the first place, the view-synthesis is used to transmit 3D video data. Note: Here one must not confuse 3D Video with the well known stereo video as in 3D cinemas. In contrast to stereo-video, where only two video streams for the right and left eye are showed, 3D video displays show many perspectives simultaneously. This is of course only possible with [auto-stereoscopic displays](http://en.wikipedia.org/wiki/Autostereoscopy). Depending on the angle you look at this display you will see a different image - without any annoying 3D glasses. However, in order to reduce the huge amount of data for all of these images, not all angles are getting transferred. Instead, we use view-synthesis to create these images afterwards. This is only possible if in addition to the video signals, [depth or disparity maps](http://en.wikipedia.org/wiki/Depth_map) are transferred. That means, that not only the color but also the distance to the camera is given for each pixel. The distance can be measured either with a special device, e.g. the [Microsoft Kinect camera](http://en.wikipedia.org/wiki/Kinect), or can be calculated in afterwards. [![example for a depth map](http://upload.wikimedia.org/wikipedia/commons/d/dd/2D_plus_depth.png)](http://upload.wikimedia.org/wikipedia/commons/d/dd/2D_plus_depth.png)

# Accelerated Implementation

I didn't invent, nor extend or improve this method. My task was to improve the speed of the view-synthesis. I tried to achieve this by doing a large part of the calculations on the graphics card instead of on the CPU. Graphics cards have the advantage that they can do many similar calculations in parallel - that 's just what I need for view-synthesis.

# What did I achieve?
For the actual application, namely "offline" view synthesis: calculate, store and watch afterwards - my implementation unfortunately did not bring a significant improvement. The reason for this is the data-transfer to the graphics card (and especially back again), which takes to long. However, if you don't want to save the data, but show it directly on screen, my implementation performs quite good. Therefore I wrote a program that reads a 3D video and then performs a view-synthesis and displays the result in a window. The point of view (camera position) can be changed either with the mouse, or adapted to the position of your head by [tracking](http://en.wikipedia.org/wiki/Head_tracking) with a webcam, while the video is playing.

# Demo-Anwendung

[![Video of a demonstration of the demo application](/images/yt/view-synth.jpg "click to go to play video on youtube")](https://youtu.be/toVHm2jQFAU)

My comments are in German, sorry.

The application was developed with Qt and OpenGL. The [EHCI library](http://code.google.com/p/ehci/) was used for head-tracking. Only raw video data in YUV format can be played back. Depth maps are also necessary in addition to the videos. Some example sequences can be found on the [FTP-server](ftp://ftp.hhi.de/HHIMPEG3DV) of the [Fraunhofer Heinrich Hertz Institute](http://www.hhi.fraunhofer.de).

* Server: ftp.hhi.de
* Verzeichnis: HHIMPEG3DV
* Benutzername: mpeg3dv
* Passwort: Cah#K9xu

Version 0.1 contains a config-file for the following YUV-Files:

* Book-Arrival-Sequence: 
   [1](ftp://mpeg3dv@ftp.hhi.de/HHIMPEG3DV/sequences/scene_book_arrival/depth/LG/best/book_depth_08.yuv)
   [2](ftp://mpeg3dv@ftp.hhi.de/HHIMPEG3DV/sequences/scene_book_arrival/depth/LG/best/book_depth_10.yuv)
   [3](ftp://mpeg3dv@ftp.hhi.de/HHIMPEG3DV/sequences/scene_book_arrival/registered/BookArrival_Cam08.yuv)
   [4](ftp://mpeg3dv@ftp.hhi.de/HHIMPEG3DV/sequences/scene_book_arrival/registered/BookArrival_Cam10.yuv)

# Download
The [Institute of Electrical Communication Engineering](http://www.ient.rwth-aachen.de) of the [RWTH Aachen](http://www.rwth-aachen.de) kindly allowed me to publish the source code. There is a Git repository on [Sourceforge](http://sourceforge.net/p/qtviewsynth).

```
git clone git://git.code.sf.net/p/qtviewsynth/code qtviewsynth-code
```

You can also download the [pre-build binaries](http://sourceforge.net/projects/qtviewsynth/files/).

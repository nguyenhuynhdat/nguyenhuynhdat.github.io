---
layout: default
title: MULTIMEDIA APPLICATIONS
description: We will install a video player, a music player, a media converter, an image suite, an image viewer and a better screenshoter. We also install pavucontrol to easily select audio output.
---

### 1. Play audio and video with VLC

[www.videolan.org](www.videolan.org)

Vlc have it own codec pack, so you do not need to install any others. It will play any media format out of the box.

```
apt-get install vlc
```
It has ability for choosing audio output. This feature was essential for me because I wanted to output to various ends - Usb soundcard, on board soundcard, HDMI... The problem was that I wanted each media program having a specific output. Eventually I had to install **PulseAudio** and **Pavucontrol** to get rid of the nuisance.

### 2. Play music and other audio with Audacious:

[http://audacious-media-player.org/](http://audacious-media-player.org/)

At first, I chose **Audacious** just because of the **"grey"** theme (will show you where to get). But now, after years of use, I love its lightweight feature and the ability to change sound card easily (I use a USB DAC/AMP).
```
apt-get install audacious
```
Here is where to get that **"grey"** theme:

[http://gnome-look.org/content/show.php/?content=135104](http://gnome-look.org/content/show.php/?content=135104)

My **Audacious** with the **grey** theme:

![audacious]({{site.baseurl}}/images/Music-With-Audacious-Bluetooth.jpg)

### 3. Cmus as text based music player

[https://cmus.github.io/](https://cmus.github.io/)

Though we have a lot other options for GUI music players, I still want to introduce you to this text base (console) music player **CMUS** for its ability to manage large music library.
```
apt-get install cmus
```

It runs directly from your terminal emulator. To initiate it, in a terminal enter **cmus** command.

It uses keyboard shortcut to control, please go here to know more about it: [https://wiki.archlinux.org/index.php/Cmus#Adding_Music](https://wiki.archlinux.org/index.php/Cmus#Adding_Music)

### 4. Pavucontrol to specify audio output

To install:
```
apt-get install pavucontrol
```
To select specific output for each programs:

![pavucontrol]({{site.baseurl}}/images/pavucontrol.png)

### 5. FFmpeg as movie/music converter

[https://www.ffmpeg.org/](https://www.ffmpeg.org/)
```
apt-get install ffmpeg
````
It’s has a lot of presets (available converting profiles) for you to choose. You can create one but I find the defaults are more than enough.

When I was learning English, I converted a lot of episodes of "the Friends" TV series into .mp3 using FFmpeg, put it on my mp3 player to hone my listening skill whenever I had time.

### 6. Gimp as image suite

[https://www.gimp.org/](https://www.gimp.org/)
```
apt-get install gimp
```
With my primitive demand on an Image manipulating app, Gimp can be compared head to head with Photoshop CS (its interface is different from Photoshop). It may take you some time to get familiar with the interface and tools.

In my opinion, what preventing a new user to using Gimp is the lack of guides and courses. I have recently found that Udemy have some course for Gimp, you should check them out.

### 7. Viewnior as image viewer

[http://siyanpanayotov.com/project/viewnior/](http://siyanpanayotov.com/project/viewnior/)

Viewnior is a very fast and competent image viewer. I always hate image viewer that take even seconds to load its library or an image.
```
apt-get install viewnior
```

### 8. Shutter for screen capture

[http://shutter-project.org/](http://shutter-project.org/)

Shutter is powerful! It gives you a lot of options (which windows, which menu, which area of the screen..) to capture your screen and give you the tools to edit captured image. In fact, almost all images on this website are captured by Shutter.
```
apt-get install shutter
```
![shutter]({{site.baseurl}}/images/shutter.png)

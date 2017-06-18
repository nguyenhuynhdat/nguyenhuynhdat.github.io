---
layout: default
title: ESSENTIAL OPERATING SYSTEM FEATURES
description: Common features of an Operating System
---

## Essential operating system features
  + Login manager
  + Notification mechanism
  + Audio driver
  + Windows fonts
  + App got taking screenshot
  + App for locking screen
  + [App launcher](http://localhost:4000/lessons/m35-essential-operating-system-features.html#applauncher)

### 1. Login manager

A login manager asks users for their credentials, lets users select which session they want to use... then transfers users to their GUI accordingly.  

**lightdm**
```
sudo apt-get install lightdm lightdm-gtk-greeter
```
**lightdm** is a lightweight yet functional login manager.

The **lightdm-gtk-greeter** is for handling the gtk theme of Lightdm (the other theme handlers are: lightdm-kde-greeter, lightdm-unity-greeter...).

My favorite Lightdm gtk theme the one from **hhh**'s here on Crunchbang forums, I have been using it from then. Just change the background and it will never get old:

[https://crunchbang.org/forums/viewtopic.php?pid=422724](https://crunchbang.org/forums/viewtopic.php?pid=422724)

<span style="color:blue">***The below is totally unnecessary, but it is nice to having another option:***</span>

I used to have a bad experience with **slim** login manager suddenly refusing to work after an update and it only gave me with a blank black screen. Although it was just a minor bug and I was easy to get **slim** to work again, I had to find another work around. **There was a choice of not using any loggin manager.**

```
geany ~/.profile
```
We will add some lines into **~/.profile** file in your home folder:
```
# startx after login
if [[ -z $DISPLAY ]] && [[ $(tty) = /dev/tty1 ]]; then
exec startx
fi
```
Now as soon as you have entered your login credential, the GUI will be launched.

### 2. Notification mechanism

Your operating system needs a way to notify you when an event happens (an email is received, your battery is low, a download is finished...)
```
sudo apt-get install xfce4-notifyd
```
Any program that needs a desktop notification (Thunderbird, Transmission...) will have a tool for displaying their messages (in a form of bubbles popping out on your desktop)

To configure how would the notification will be like:

```
xfce4-notifyd-config
```

![notification bubble]({{site.baseurl}}/images/xfce4-notifyd-fullwindow.png)

### 3. Audio driver

* Alsa will give you the audio driver
* PulseAudio will give you multiple choices over the output.

I recommend to use them both on your system. I used to hate PulseAudio, but after having some USB DAC, PulseAudio really makes my life easier.

```
sudo apt-get install alsa-base alsa-utils pulseaudio pavucontrol
```
You should have the sound working immediately, if not, follow by this command:
```
alsactl init
```
In your terminal using the command Alsamixer to open the mixer and pressing "SPACE" key to unmute all the channels.
```
alsamixer
```
![alsamixer]({{site.baseurl}}/images/alsamixer.jpg)

### 4. Windows fonts
Lacking windows fonts, some websites and documents will not display nicely as expected (Especially documents received from someone using Windows). To install Windows fonts:
```
sudo apt-get install ttf-mscorefonts-installer
```
(These fonts are free).

### 5. App got taking screenshot
Printing screen/ screen capturing program: **scrot**

To use **scrot**, in a terminal window, type:
```
scrot -d 5 -c
```
![taking_screenshot]({{site.baseurl}}/images/taking_screenshot.jpg)

It will take a screen shot after 5 seconds and display the countdown (-d for delaying and -c for displaying the countdown).

The captured image will be saved in your home folder.

This **scrot** command should be bound to the **PRINT SCREEN** key on your keyboard for convenience. I have configured that in the rc.xml, and the entry for it looks like this:
```
<keybind key="Print">
  <action name="Execute">
    <command>scrot -cd1</command>
  </action>
</keybind>
```

### 6. App for locking screen
To lock screen with **light-locker**:

Locking screen for me is a must-have feature since I often works at various places and my normal working section often takes too long to be able to always attend at my laptop.

I choose **light-locker** for its nature of lightweight and simple.
```
sudo apt-get install light-locker
```
Bind **Windows + l** these keys to the following command:
```
$ light-locker-command -l
```
in my rc.xml file. The entry looks like this:
```
<keybind key="W-l">
  <action name="Execute">
    <startupnotify>
      <enabled>true</enabled>
      <name>lock</name>
    </startupnotify>
    <command>light-locker-command -l</command>
  </action>
</keybind>
```
### 7. Apps launcher <a name="applauncher"></a>

Quickly launch a program with gmrun:

**gmrun** give you the ability to quickly launch a program or run a command by just using your keyboard. To make it is even easier, it has an auto-complete feature that will recommend you a list of commands that have already installed in your system based on what you have type:

![gmrun]({{site.baseurl}}/images/gmrun.png)

To install:
```
sudo apt-get install gmrun
```
In my my rc.xml file, the **gmrun** have been bound into **“Windows key + R”**.
Press these combination keys and **gmrun** window should be ready.

Already "equipped" with a right-click menu and a bunch of shortcut keys, now with this a launcher the convenience of launching a program of Openbox system is top notch.

Here is how the key binding entry for **gmrun** looks like in my **rc.xml**:
```
</keybind>
<keybind key="W-r">
  <action name="Execute">
    <startupnotify>
      <enabled>true</enabled>
      <name>gmrun</name>
    </startupnotify>
    <command>gmrun</command>
  </action>
</keybind>
```

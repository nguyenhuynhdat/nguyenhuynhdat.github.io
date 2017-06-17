---
layout: default
title: ESSENTIAL OPERATING SYSTEM FEATURES
description: install notification mechanism, audio driver, Windows fonts, app for taking screenshot, screen locker.
---

## Essential operating system features
  + Notification mechanism
  + Audio driver
  + Windows fonts
  + App got taking screenshot
  + App for locking screen
### 1. Login manager

**lightdm**
```
sudo apt-get install lightdm lightdm-gtk-greeter
```
**lightdm** is a lightweight yet functional login manager. A loggin manager manages loggin attempts and  prompts the user for credentials, lets the user select a session..

***The below is totally unnecessary, but it is nice to having another option:***
I used to have a bad experience with a loggin manager suddenly refusing to work after an update and it left with a blank black screen. Although it was just a minor bug and I was easy to get slim to work again, there is a choice of not using any loggin manager.

The only nuisance left is that you have to initiate your desktop with **startx** command whenever you fire up your computer. To work around it you need to do the following.
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
Your operating system needs a way to notify you when an event happens (an email is received, your battery is low…).
```
sudo apt-get install xfce4-notifyd
```
Now, any program that needs desktop notification (Thunderbird, Transmission...) should have a tool for displaying their messages ( in a form of bubbles popping out on your desktop)

To configure how would the notification be like:

```
xfce4-notifyd-config
```

![notification bubble]({{site.baseurl}}/images/xfce4-notifyd-fullwindow.png)

### 2. Audio driver

What gives you the driver is Alsa and what gives you multiple choice over output is PulseAudio.
It is recommended to use both on your system.

```
sudo apt-get install alsa-base alsa-utils pulseaudio pavucontrol
```
You should get sound work immediately, if not, follow by entering this command:
```
alsactl init
```
In your terminal using the command Alsamixer to open the mixer and pressing "SPACE" key to unmute all the channels.
```
alsamixer
```

### 3. Windows fonts
Lacking windows fonts, some website and documents will not display nicely (Especially documents received from someone using Windows). To install Windows fonts:
```
sudo apt-get install ttf-mscorefonts-installer
```
These fonts are free by the way.
### 4. App got taking screenshot
Printing screen/ screen capturing program: **scrot**

To use **scrot**, in a terminal window, type:
```
scrot -d 5 -c
```
It will take a screen shot after 5 seconds and display the countdown (-d for delaying and -c for displaying the countdown).

The captured image will be saved in your home folder.

This **scrot** command should be bound to the **PRINT SCREEN** key on your keyboard for convenience. I have configured that in the rc.xml file like this:
```
<keybind key="Print">
  <action name="Execute">
    <command>scrot -cd1</command>
  </action>
</keybind>
```
### 5. App for locking screen
To lock screen with **light-locker**:

Lock screen for me is must-have feature as I often worked at various places and my normal working section often takes too long to be able to always attend at my laptop.

I am choosing **light-locker** for its nature of lightweight and simple.
```
sudo apt-get install light-locker
```
Bind **Windows + l** these keys to the following command:
```
$ light-locker-command -l
```
in your rc.xml file. The entry will look like this:
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
### 6. Apps launcher

Quickly launch a program with gmrun:

**gmrun** give you the ability to quickly launch a program or run a command by just using your keyboard. To make it is easier it will recommend you a list of commands that have already installed in your system based on what you have type:

![gmrun]({{site.baseurl}}/images/gmrun.png)

To install:
```
Sudo apt-get install gmrun
```
In my my rc.xml file, the **gmrun** have been bound into **“Windows key + R”**.
Press these combination keys and **gmrun** window should be ready.

Already "Equipped" with a right-click menu and a bunch of shortcut keys, now with this a launcher the convenience of launching a program in Openbox system is top notch.

Here is how the key binding entry look like in my rc.xml:
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

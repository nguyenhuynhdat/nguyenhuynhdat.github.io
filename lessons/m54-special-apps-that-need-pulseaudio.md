---
layout: default
title: OFFICE APPLICATIONS
description: install a word processor, a spreedsheet, a pdf reader and an ebook reader.
---
When it come to audio, Linux actually falls short comparing to its rival Mac OS or Windows (I use various Audio cards on my Windows PC. With Windows, it's just a breeze). I am no expert on this audio business but I have use Debian/Ubuntu for a long time and all of my problems with audio often came from Pulseaudio. Thus, in this guide, I tried my best to avoid using it. Despite of that reason, in real life some of my day to day application specifically need Pulseaudio!

to install pulseaudio

sudo apt-get install pulseaudio

[spacer height="25px"]
1. Skype as VOIP client

http://www.skype.com/en/

First you need to enable “partners” repository:

Sudo nano /etc/apt/sourcelist

Comment out the line (delete the # at the beginning of the line):

##Skype
#deb http://archive.canonical.com/ubuntu/ trusty partner

Then

Sudo apt-get update

Sudo apt-get install skype

Login and you all set!

Below is the actual screenshot on my Laptop.

 Skype
2. Kazam as screen recording

https://apps.ubuntu.com/cat/applications/kazam/

My freelancer job requires a lot of short video demonstrating my instructions. Kazam is easier to use, let you choose one from various installed microphones, records the screen nicely with great output (small size and in HD resolution).

Sudo apt-get install kazam

Kazam

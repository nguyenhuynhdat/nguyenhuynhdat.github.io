---
layout: default
title: ICON THEME
description: install and configure an icon theme.
---

Take a look at two Thunar windows in the screenshot. I have applied “AwOken” icon set (its name is really written like that, not a typo)

To install a icon theme, either install via PPAs or copy (the extracted) icon folder directly to /usr/share/icons or ~/.icons

Adding a PPA is often frowned upon, but since the PPA for AwOken theme is really popular. The risk is low!

You need to install **software-properties-common** to be able to add PPA using command line, to install it:
```
sudo apt-get install software-properties-common
```
Here is how I have installed AwOken icon theme, as guided here:

http://gnome-look.org/content/show.php/AwOken?content=126344

sudo add-apt-repository ppa:alecive/antigone

sudo apt-get update

sudo apt-get install awoken-icon-theme

AwOken is a special theme that have it own script to customize itself, here is the instruction given by the author, skim through it and you will see how awesome it is: [Installation and Instructions (PDF)]({{site.baseurl}}/assets/Installation_and_Instructions.pdf)

Or if you want to learn by doing, below is the command to trigger all the options. The instruction a long the way is easy to understand and follow:
```
awoken-icon-theme-customization
```
Apply the icon theme.

Open Lxappearance to change the icon-theme to AwOken.

Here is how the icon theme is on my system:

![awaken folder]({{site.baseurl}}/images/awokenfolder.png)

![awaken apps]({{site.baseurl}}/images/awokenapplications.png)

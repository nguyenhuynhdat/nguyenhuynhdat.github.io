---
layout: default
title: ESSENTIAL DESKTOP ENVIRONMENT COMPONENTS
description: install taskbar, file manager, wallpaper manager, network manager and power manager.
---

## Essential desktop environment Components
  + Taskbar
  + File manager (with achieve manager)
  + App for setting wallpaper
  + Network manager
  + Power manager

### 1. Taskbar

Initially I have been using **tint2** for taskbar, but while reinstalling my Laptop with Debian Jessie, I have remembered that a good person (an reader of this website, infact :D) recommended **lxpanel**. I gave it a try and have been using ever since. It is *really really* nice!

Although I understand the completeness and quick set-up of **lxpalnel**, **tint2** is still awesome in its own way.

**Please try both and decide for yourself!**

**LXPANEL**:
Lxpanel is a lightweight yet fully equipped with
all the necessary plugins (system tray, menu...)

```
sudo apt-get install lxpanel
```

Here is some configuration that I have done to my **lxpanel** to make it look nicer and be customized to my requirement:

* Make it use the system theme:
**right-click** > **Panel settings** to access panel references > **Appearance** tab > tick **System theme** in the **Background** section.

![lxpanelSystemtheme]({{site.baseurl}}/images/Panel Preferences_Systemtheme.png)

* I have borrow the awesome and mature logout script from [**bunsenlabs**](https://www.bunsenlabs.org/) distro [here](https://github.com/BunsenLabs/bunsen-exit)

(I do not know if borrowing it this way is okay or not, but I hope the developer will understand my pure purpose here and give me his/ her approval. I will ask him/ her as soon as possible)

Download it and then put it somewhere convenience, say: **/home/user/Custom/bl-exit**

*I always think it is a good practice to save all your special scripts in one "Custom" folder for it is easier to make backup and transfer in the future*

**right-click** > **Panel settings** to access panel references > **Advanced** tab > type below command in the **Logout Command** box in the **Set preferred applications** section.
```
python /home/dat/Custom/bl-exit
```

![lxpanelSystemtheme]({{site.baseurl}}/images/Panel Preferences_Logout.png)

Now you have a very nice logout interface with various choices:

![bl-exit]({{site.baseurl}}/images/blexit.png)

**TINT2**:

***Please install bl-exit from the above section because in this tint2 configuration I also use the script***

To install **tint2**
```
sudo apt-get install tint2
```
Tint2 is a full feature, customizable yet lightweight enough even for a minimal enthusiast.

With its default settings, tint2 will look extremely ugly. So again we will use my configuration file. The new tint2 will look like this:

![tint2taskbar]({{site.baseurl}}/images/tint2.png)

Here is configuration on pastebin, [click here!](https://pastebin.com/hxYLwYjw)

Copy the content to replace the current one.

```
geany ~/.config/tint2/tint2rc
```

I have borrowed this configuration from someone on Crunchbang forum and do not remember specifically whom. It has been my favorite Tint2 ever since, and I sincerely want to give the author my grateful respect.

Besides its aesthetic look, a more special feature of this config is to give us a transparency taskbar without using any compositor. This maybe a good thing because some graphics cards does not behave nicely with compositor.

With this **tint2**, you will need these two packages:
* **gsimplecal** for a Calendar
* **volti** for volume adjustment

```
sudo apt-get install gsimplecal volti
```

**BATTERY ICON ON SYSTEM TRAY**

The battery icon on your system tray will come from a power manager application. My current one is from **mate-power-manager**. *Please go to the 6th section of this page to know more about it.*

There are also some scripts that can monitor your battery and place an icon on system tray (to name a few: cbatticon, tidybattery...), but they often need to be compiled (installed) from source. Therefore, it may depend on you to solving the missing/ conflicting of dependencies. I want to have a safe and easy to be installed system, so a power manager is an obvious choice.

### 2. File manager (with achieve manager)

There is nothing much to say about a file manager as it should be quite familiar. **Thunar** is just easy to use with a short and intuitive learning curve.

```
sudo apt-get install thunar thunar-volman thunar-archive-plugin thunar-media-tags-plugin humanity-icon-theme gvfs gvfs-backends
```

You have to install some more packages along with **thunar** for it can have enough features (the additional features: add thumbnails, add achieve entries to Thunar menu, add sharing file accessibility...)

![thunar]({{site.baseurl}}/images/Panel Preferences_Systemtheme.png)

**USE CATFISH TO SEARCH FILE AND INTEGRATE IT TO THUNAR RIGHT-CLICK MENU**

**catfish** is a searching files application, easy to use and does the job gracefully, which can integrate into **Thunar** using its ***"custom action"*** feature.

_**To install:**_
```
sudo apt-get install catfish
```

_**To integrate it into Thunar**_

In **Thunar** > **Edit** > **Configure custom action** > **Edit action** to edit both of the tabs as showing bellow:

```
catfish --path=%f
```
![editactionCommand]({{site.baseurl}}/images/Edit Action_c.png)

![editactionFiletype]({{site.baseurl}}/images/Edit Action_t.png)

Now you have an entry on **Thunar** right-click menu for searching files & folders.

![SearchThunar]({{site.baseurl}}/images/RMenuThunar.png)

### 3. Archive manager

Install an archive manager and compression utilities:

```
sudo apt-get install file-roller rar unrar p7zip zip unzip p7zip-full p7zip-rar
```

After installing these packages, you will have full compressing/decompressing power in your right click menu (when you are in Thunar).

![fileroller]({{site.baseurl}}/images/File_Roller.png)

### 4. App for setting wallpaper

I chose Nitrogen for wallpaper manager.

```
sudo apt-get install nitrogen
```

If you are using the my config for your openbox, the entry of “Choose Wallpaper” (under the “Settings” entry) in the right-click menu has set  to point to a folder name “Wallpapers” in **/home/user** directory, you have to create that folder and copy your favorite wallpapers into it.

In my **menu.xml** the entry for **Nitrogen**:
```
<item label="Choose Wallpaper">
  <action name="Execute">
    <command>nitrogen ~/Wallpapers/</command>
	</action>
</item>
```

To create a Wallpapers folder:
```
mkdir ~/Wallpapers
```

Now testing it by **Right-click** > **Settings** > **Choose Wallpaper** and **Apply**!

![nitrogen]({{site.baseurl}}/images/nitrogen.png)

### 5. Network manager

**wicd** is a standalone (not depending any desktop environment) and full feature network manager:

To install:
```
sudo apt-get install wicd
```

How to use it is pretty straight forward, please tinker it yourself.

![wicd]({{site.baseurl}}/images/wicd.png)

Wicd oftions:

![wicdoption]({{site.baseurl}}/images/wicdoption.png)

You can see how I configure my network to use Google DNS.

### 6. Power manager

Over the course of using Linux I have changed power manager applications from time to time. Currently I find that the one form Mate desktop environment is the most suitable for Debian Jessie Openbox.

Besides controlling the power references, the power manager also gives **lxpanel/ tint2** a nice battery icon (Laptop only)

```
sudo apt-get install mate-power-manager
```
![wicdoption]({{site.baseurl}}/images/Power Management Preferences.png)

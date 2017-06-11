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

Initially I have been using **tint2** for taskbar, but after reinstall Openbox with Ubuntu 16.04. After remembering a good person have recommended **lxpanel**, I have been Using ever since.

Although I understand the completeness and quick set-up of **lxpalnel**, **tint2** is still awesome in its own way, the customizability.

Please try both!

**LXPANEL**:
Lxpanel is a lightweight yet fully equipped with
all the necessary plugins (from volume adjusting to menu...)

```
sudo apt-get install lxpanel
```

Here is some configuration that I have make to my **lxpanel**:

* Make it use the system theme:
**right-click** > **Panel settings** to access panel references > **Appearance** tab > tick **System theme** in the **Background** section.

![lxpanelSystemtheme]({{site.baseurl}}/images/Panel Preferences_Systemtheme.png)

* I have borrow the awesome and mature logout script from [**bunsenlabs**](https://www.bunsenlabs.org/) distro [here](https://github.com/BunsenLabs/bunsen-exit):

Download it and then put it somewhere convenience to access, say: **/home/user/Custom/bl-exit**

**right-click** > **Panel settings** to access panel references > **Advanced** tab > type below command in the **Logout Command** box in the **Set preferred applications** section.
```
python /home/dat/Custom/bl-exit
```

![lxpanelSystemtheme]({{site.baseurl}}/images/Panel Preferences_Logout.png)

Now you have a very nice logout interface with enough choices:

![bl-exit]({{site.baseurl}}/images/blexit.png)

**TINT2**:

***Please install bl-exit from the above section because in my tint2 configuration file I also use the script to logout***

To install **tint2**
```
sudo apt-get install tint2
```
Tint2 is a full feature, customizable yet lightweight enough even for a minimal enthusiast.
With its default setting, tint2 will look extremely ugly. So again we will use my configuration file.

![tint2taskbar]({{site.baseurl}}/images/tint2.png)

My configuration on pastebin, [here!](https://pastebin.com/hxYLwYjw)

Copy this content to replace the current one.

```
geany ~/.config/tint2/tint2rc
```

I have borrowed this configuration from someone on Crunchbang forum and do not remember specifically whom. It has been my favorite Tint2 since. Please let me give him or her my respect!

With **tint2**, you need these two package:
* **gsimplecal** for a Calendar
* **volti** for volume adjustment

```
sudo apt-get install gsimplecal volti
```
**BATTERY ICON ON SYSTEM TRAY**
To have it you have to install a power manager application. My current one is from **Mate** desktop environment. Please go to the 6th section of this page to know more about it.

There are also some scripts that monitor your battery and place a icon on **lxpanel** system tray (to name a few: cbatticon, tidybattery...), but they often need to be compiled (installed) from source code. This way, it will depend on you to solving the missing/ conflicting of dependencies. I want you to have a safe and easy installed system, so a power manager is an obvious choice.

### 2. File manager (with achieve manager)

There is nothing much to say about a file manager as it is critical for your user's experience. **Thunar** is just easy to use like most of file manager, intuitive and short learning curve.

```
sudo apt-get install thunar thunar-volman thunar-archive-plugin thunar-media-tags-plugin humanity-icon-theme gvfs gvfs-backends
```

Along with the main package, for Thunar can have enough features we need to install some more (the additional features: add icon, add achieve entries to Thunar menu, add sharing file accessibility...)

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

Now you have a entry on **Thunar** right click menu for searching files & folders.

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
My entry of “Choose Wallpaper” (under the “Settings” entry) in your right click menu has set  to point to a folder name “Wallpapers” in my home directory, I have to create that folder and copy my favorite wallpapers into it.

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

Over the course of using Linux I have changed power manager applications from time to time. Currently I find that the one form Mate desktop environment is the most suitable.

Besides control the power references, the power manager also gives **lxpanel/ tint2** a nice battery icon (Laptop only)

```
sudo apt-get install mate-power-manager
```
![wicdoption]({{site.baseurl}}/images/Power Management Preferences.png)

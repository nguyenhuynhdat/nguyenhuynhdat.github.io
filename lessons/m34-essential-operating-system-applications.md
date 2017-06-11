---
layout: default
title: ESSENTIAL OPERATING SYSTEM APPLICATIONS
description: install terminal emulator, text editor, GUI package manager, task manager.
---

## Essential operating system application
  + Terminal emulator
  + Text editor
  + Synaptic (GUI package manager)
  + Gdebi
  + Task manager (System monitor)

### 1. Terminal emulator
1. Terminator for Ubuntu Openbox terminal emulator

Using Linux, you need a terminal emulator (of course, you can live without but much easier if you know how to use one). A terminal acts as a mediator to pass your command to your OS.

Terminator is a good terminal emulator with tabs support and it can be split in to terminal windows both horizontally and vertically.
```
sudo apt-get install terminator
```
Some useful keyboard shortcut:
* **F11**: Toggle fullscreen
* **Ctrl + Shift+ O**: Split terminals horizontally
* **Ctrl + Shift+ E**: Split terminals vertically
* **Ctrl + Shift+ T**: Open new tab

![terminator]({{site.baseurl}}/images/Terminal_split.jpg)

### 2. Text editor

You always need a text editor when using Linux as all its configuration file is in text form. If you are a developer and write code in on a daily basis, Geany is also a very good text editor with its variation of plugins.

I am choosing Geany because it came as default with Crunchbang, my beloved distro. Just do not want to change to any other.
```
sudo apt-get install geany
```

We often combine **geany** with **gksudo** command to edit system files. Do not combine it with sudo (it will mess up Geany configuration file).

```
gksudo geany /etc/fstab
```

Just remember this rule: **sudo** are for application in terminal, for Graphical one, you need to use **gksudo** instead. Otherwise, you will mess them up.

![geany]({{site.baseurl}}/images/Geany.png)

### 3. Synaptic
**Synaptic** – GUI package manager

Up until now, you have installed software mainly by **apt-get** via terminal, there is another good option to install them via a GUI package manager, Synaptic is always my first choice. It was extremely useful when you need to find a recommended packages when you install a minimal desktop.

```
sudo apt-get install synaptic
```

Here is how the status of Firefox and its recommends are showing in Synaptic:

![synaptic]({{site.baseurl}}/images/Synaptic-package-manager.jpg)

I do not use Synaptic much. **apt-get** is enough for managing package because now I really familiar with all applications I am using (know them by name and which of their recommended packages I need).

### 4. Gdebi
**Gdebi** to install .deb package

Gdebi is also a nice program to handle .deb files, the standard package in Debian. After you have had Gdebi installed, whenever you want to install a .deb file, just double click it. Not recommend though, you should ***REALLY*** know what you are doing when dealing with packages which are outside of your official repository.
```
sudo apt-get install gdebi
```
Another alternative if you do not use gdebi: One simple command can do it:
```
sudo dpkg -i deb_package #(to remove: sudo dpkg -r deb_package)
```

![gdebi]({{site.baseurl}}/images/gdebi.png)

### 5. Task manager (System monitor)
System monitor application - **htop**

Htop is a lightweight program and do the job just fine.
```
sudo apt-get install htop
```
In your terminal emulator, type htop, it will display all the running processes and the resources being used at that moment.

![htop]({{site.baseurl}}/images/htop.png)

As you can see here, I installed an Ubuntu 64bit on my computer, and the amount of RAM it takes on startup is just 390MB. That’s actually great comparing with other desktop environment, and if I go this way with 32bit, it's easier to get to just slightly over 200MB of RAM.

Here is how to bind the old combination keys **Ctrl + Alt + Del** to **htop** in your Openbox **rc.xml** configuration file:
```
<keybind key="C-A-Delete">
  <action name="Execute">
    <startupnotify>
      <enabled>true</enabled>
      <name>htop</name>
    </startupnotify>
    <command>terminator -e htop</command>
  </action>
</keybind>
```

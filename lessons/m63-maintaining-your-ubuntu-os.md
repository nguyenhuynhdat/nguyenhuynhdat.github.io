---
layout: default
title: MAINTAIN YOUR UBUNTU/ DEBIAN SYSTEM
description: introduce some "house keeping" tasks for a Debian system.
---

### 1. Update your system frequently

Just be familiar with two below commands and you will be good to go:
```
sudo apt-get update
```
It will update the information **apt** is having from all repositories in **/etc/apt/source.list** file.

This command does not install package, just update information.

The following command will actually install newest version of any package that has been **already** installed in your system (if any).
```
sudo apt-get upgrade
```
You should always remember to do it one in a while (I prefer once a week) to keep your system up to date.

Or just:
```
sudo apt-get update && sudo apt-get upgrade
```
The **“&&”** part is for telling the terminal only run the **upgrade** command ***if only*** the **update** command has been finished.

_**_TO SUM UP:_**_

  *  **update**: get information about what is the newest version of any package on the repository.
  *  **upgrade**: compare the version of each package installed on your computer and download the newest version of them if any.

### 2. Keep your system clean

Cleaning up the cache of **apt**:

**apt** is keeping all the downloaded binary files (.deb) after any of your installation/update. It does so to keep these **.debs** file available in case you want to reinstall or repair.

That means if you clear this cache and when the need arises later, you have to re-download.

To see how much apt has been cached **.deb** files:

First, go to the apt cache directory by:
```
cd /var/cache/apt/archives
```
then:
```
du -ch
```
**du -ch** mean:

 * **du**: disk usage command - return the size of a directory
 * **c**: for returning the total
 * **h**: human - easier for us to read the output (the size will be in Megabyte measurement unit)

The command **apt-get clean** will ***clear all*** of the cache.
```
sudo apt-get clean
```

OR only ***downsizing*** the apt cache:
```
sudo apt-get autoclean
```

The **autoclean** is a more compromising way if you want to keep apt's cache locally in a reasonable size. It only deletes the packages that are deemed useless (partial packages).

To clean up of any unused dependencies that was left behind after you remove a package:
```
sudo apt-get autoremove
```

### 3. Analyzed the usage of your disk to track where your disk space has gone.

We will use a very good program call **Baobab** (Disk Usage Analyzer).
```
apt-get install baobab
```
You should start it with root privilege to get the most information possible.
```
gksu baobab
```
Disk Usage Analyzer

![baobab]({{site.baseurl}}/images/Disk-Usage-Analyzer.jpg)

### 4. Monitor your system

If you feel that something has gone wrong: suddenly your fan running fast, your computer slowing down… you should use **htop** to find out if there are programs hogging your system resources (using a lot of CPU power or RAM).

Problem like this often happens when there is a program which requires resources that beyond the capability of your system or simply because a program is not configured correctly. For the former case, you have to find another lightweight alternative. For the later, here is my own experience: I used to encounter a problem with my video configuration. The video playback did not use GPU power but used CPU power instead causing extremely high CPU usage for no obvious reason. After tracking the problem down, I then reconfigured my GPU and everything was fine.

These are typical cases that you should using system monitor to detect which is the culprit.

You may need to **kill** that process (to terminate it) for further step can be taken.

To ***kill*** a running program the hard way (force it to close) by using command in terminal when the normal way of clicking the close button on its windows do not have any effect (that program is hanging or something).

You can terminate a running program:
```
killall [program_name]
```

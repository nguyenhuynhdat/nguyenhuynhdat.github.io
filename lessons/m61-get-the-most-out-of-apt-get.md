---
layout: default
title: GET THE MOST OUT OF APT-GET
description: introduce some other apt-get commands.
---

Ubuntu/ Debian use **Apt (Advanced Package Tool)** as their package manager (a tool that assist you on resolving dependencies when you need to install, upgrade, configure, and remove packages).

Through out this guide, we only use mostly the command **apt-get install**. In this lesson, I will show you how to get the most out of **Apt** package manger.

### It all starts with update repositories information:
```
apt-get update
```
### To update entire of system:
```
apt-get upgrade
```
<span style="color:red">Although name **"upgrade"**, the command is only for update packages that are already installed in your system.</span>

### To install and update a package
```
apt-get install [package name]
```
The command also update that package if it has already installed.

### To install a package without its recommends (this is the case of installing a minimal Ubuntu/Debian desktop)

To do that you need to specify this flag: <span style="color:blue">--no-install-recommends</span>

```
apt-get install <span style="color:blue">--no-install-recommends</span> [package name]
```

### To remove a package
```
apt-get remove [package name]
```
To remove a package along with all of its configuration file:
```
apt-get --purge remove [package name]
```

### To find information about installed or can be installed packages
```
apt-cache search [package name/ related word]
```
For instance, you can search for the key word “image viewer” to find all  the info about image viewer in repositories.
```
apt-cache search “image viewer”
```
The output should be the list of packages that are related to image viewer.

### To list dependencies and recommends of a packages

It's very useful when you were trying to install a minimal Ubuntu system (mostly by using the **"--no-install-recommends"** flag) and sometimes found in a situation where some of your applications were lacking features (you need to installs some more of it recommends).
```
apt-cache depends [package name]
```

### To show the version of a package and which repository it is come from
```
apt-cache policy [package-name]
```

### To find out about information about a package
```
apt-cache show [package-name]
```
### dpkg
Although not using apt but I find the below is a essential command to supplement to apt features.
```
dpkg -s [package name]
```
In fact, I often use it rather than apt-cache show/policy.

In my experience, with just all these commands, you can effectively manage your applications and your Ubuntu system.

### To find if a package is installed on your system
```
dpkg -l [package-name]
```

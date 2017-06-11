---
layout: default
title: GET THE MOST OUT OF APT-GET
description: introduce some other apt-get commands.
---

Ubuntu/ Debian use **Apt (Advanced Package Tool)** as their package manager (a package manager is a tool that assist you on resolving dependencies when installing, upgrading, configuring, and removing software).

Through out this guide, we only use **apt-get install** to install a package. In this part of the guide, I will show you how to get the most out of **Apt** package manger.

### It all starts with update repositories information:
```
apt-get update
```
### to update entire of system:
```
apt-get upgrade
```
Although name **"upgrade"**, the command is only for update packages that are already installed in your system.

### to install and update a package
```
apt-get install [package name]
```
The command also update that package if it has already installed.

### To install a package without its recommends (this is the case of installing a minimal Ubuntu/Debian desktop)
```
apt-get install --no-install-recommends [package name]
```

### To remove a package
```
apt-get remove [package name]
```
To remove a package along with all of its configuration file
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

### To list dependencies and recommends of a packages

It's very useful when you trying to install a minimal Ubuntu system (mostly by using the **"--no-install-recommends"** flag) and sometimes find that some applications are lacking features (you need to installs some more of it recommends).
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

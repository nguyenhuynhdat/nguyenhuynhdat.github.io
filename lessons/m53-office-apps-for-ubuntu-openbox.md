---
layout: default
title: OFFICE APPLICATIONS
description: We will install a word processor, a spreedsheet, a pdf reader and an e-book reader.
---

### 1. Office suite:

For normal use of office work, LibreOffice is competent enough:

[https://www.libreoffice.org/](https://www.libreoffice.org/)

You can either install entire of this office suite or pick out only what you need. I only use two of the modules:
  * Calc: spreadsheet application.
  * Writer: word processing application.

```
apt-get install libreoffice-calc libreoffice-writer libreoffice-gtk
```

The **libreoffice-gtk** package is for **Libreoffice** can integrate nicely with the system gtk theme (other wise it will look urgly).

You can choose one from several icon sets. In the screenshot below I am using the **“sifr”** icon sets:
```
apt-get install libreoffice-style-sifr
```

Then apply it by changing the **“Icon size and styles”** (User Interface) to “sifr”, go to **Tool** > **Options** > **View**.

To enable the ability to remember the last working place in your document, you need to fill out your **“User Data”**. Go to **Tool** > **Options** > **User Data**.

If there is no user identified, every time you open a document, LibreOffice will assume a new user is opening a document and will open it at the beginning.

As a die hard user of spreadsheets, I find Calc is just a standard and for "lite" spreadsheet work only. I am intensively depending on VBA/ GAS scripts (Visual Basic for Applications come with MS office & Google Apps Script come Google Apps). Only Microsoft Excel or Google Sheet can meet my requirement.

**LibreOffice Calc**

![libreoffice-calc]({{site.baseurl}}/images/LibreOffice-Calc.jpg)

**LibreOffice Writer**

![libreoffice-writer]({{site.baseurl}}/images/LibreOffice-Writer.jpg)

### 2. Qpdfview as Pdf reader

As I had some bad experiences with Evince when I was using Crunchbang/ Debian Wheezy (Slow to navigate through a large PDF file, blurry displays of image in PDF file). Then I found **qpdfview**, quickly open any PDF and render images nicely:
```
sudo apt-get install qpdfview
```
In the old version of this website, I recommend Foxit reader (very good indeed!), but is is not native Linux, and need a PPA.

### 3. Fbreader as ebook reader

[https://fbreader.org/](https://fbreader.org/)
```
apt-get install Fbreader
```
"Supports popular ebook formats: ePub, fb2, mobi, rtf, html, plain text, and a lot of other formats" (From its website!). It's also lightweight and very fast to open ebook.

![fbreader]({{site.baseurl}}/images/fbreader.png)

**Above is the awesome Quo Vadis novel by Henryk Sienkiewicz, translated by Jeremiah Curtin.**

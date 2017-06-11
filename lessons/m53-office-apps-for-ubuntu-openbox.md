---
layout: default
title: OFFICE APPLICATIONS
description: install a word processor, a spreedsheet, a pdf reader and an ebook reader.
---

###1. Office suite:

For normal use of office work, LibreOffice is competent enough:

[https://www.libreoffice.org/](https://www.libreoffice.org/)

You can either install entire of this office suite or pick out only what you need. I only use two of the modules:

* Calc: spreadsheet application.

* Writer: word processing application.
``
apt-get install libreoffice-calc libreoffice-writer libreoffice-gtk
```

The **libreoffice-gtk** package is **Libreoffice** can integrate nicely with the system gtk theme (other wise it will look urgly).

You can choose one from several icon set. In the screenshot below I am using the **“sifr”** icon sets:
```
apt-get install libreoffice-style-sifr
```

Then apply it by changing the **“Icon size and styles”** (User Interface) to “sifr”, go to **Tool** > **Options** > **View**.

To enable the ability to remember the last working place in your document, you need to fill out your **“User Data”**. Go to **Tool** > **Options** > **User Data**.

If there is no user identified, LibreOffice will assume a new user is opening a document and will open it at the beginning.

As a die hard user of spreadsheets, Calc is just a standard and for light spreadsheet work only. I am intensively depending on VBA/ GAS script. Only Microsoft Excel or Google Sheet can meet my requirement.

LibreOffice Calc


LibreOffice Writer


### 2. qpdfview as Pdf reader

As I had some bad experiences with Evince when I was using Crunchbang/ Debian Wheezy (Slow to navigate through a large PDF file, blured displays of images in PDF file). Then I found **qpdfview**, quickly open any PDF:
```
sudo apt-get install qpdfview
```

### 3. Fbreader as ebook reader

[https://fbreader.org/](https://fbreader.org/)
```
apt-get install Fbreader
```
"Supports popular ebook formats: ePub, fb2, mobi, rtf, html, plain text, and a lot of other formats" (From its website!). It's also lightweight and very fast to open ebook.

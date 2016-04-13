---
layout: page
title: "STRUCTURE"
permalink: /documentation/structure.html
--- 

## SOURCE
This folder holds the files used by Jekyll to create our markdown files.

### Source/_includes
This folder contains the default 'common' files as well as a folder for every book you've added. You'll find two files inside every book folder; amazon.md and chapters.md. 

Chapters.md is where you'll paste your manuscript.

### Source/_layouts
This folder contains a folder for every book you've added, the files inside define what files to combine when creating each of our formats. The default layouts each combine the following files (in the following order) when creating our final markdown file for each format.

* **amazon.md**
  * Source/_includes/$BOOK-TITLE/amazon.md
    * file differs from chapters.md in that it adds `Source/_includes/amazon_review.md` directly after the contents of `chapters.md`
  * Source/_includes/magnet_tah.md
  * Source/_includes/bio.md
  * Source/_includes/bibliography.md
  * Source/_includes/license.md
* **epub.md**
  * Source/_includes/$BOOK-TITLE/chapters.md
  * Source/_includes/magnet_tah.md
  * Source/_includes/bio.md
  * Source/_includes/bibliography.md
  * Source/_includes/license.md
* **pdf.md**
  * Source/_includes/$BOOK-TITLE/chapters.md

### Source/$BOOK-TITLE
This folder defines what formats to create for each book and which layouts to use for each format.

### Source/images
This folder is used to hold any images, primarily I use it for book covers.

## _SITE
Jekyll creates this folder every time you run the `bind.sh` script. Inside you'll find the 'final' markdown files for each format that were created according to the files defined in _layouts. These are the files that we'll feed into Pandoc for conversion.

## BOOKS
This directory holds your finished books. Inside you'll find a folder for each book you've created, containing every format you've created for it.

## PANDOC
This directory holds stuff that Pandoc needs.

### Pandoc/css
This is the stylesheet used when creating epub and mobi/Amazon files.

### Pandoc/templates
This directory contains the custom templates Open-Publisher uses when converting files with Pandoc.

## MISC.
* bind.sh
  * A small bash script used to 'bind' your books.
* new.sh
  * A small bash script used to create the scaffolding Open-Publisher expects for new books.
* margins.sh
  * A mostly unused script I used to calculate margins.
* _config.yml
  * This file defines a couple things required by Jekyll.

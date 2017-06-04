---
layout: page
title: "REQUIREMENTS"
permalink: /documentation/requirements.html
--- 
I recommend using our [Dockerfile](/Open-Publisher-Documentation/use/docker.html) to build the Docker container since it'll have all the tools you need, but if you want to install everything locally Open-Publisher needs the following software and tools to installed in order to work:

## Ruby 2.x
Jekyll requires ruby so you'll need a working Ruby installation.

## Jekyll
[Jekyll](https://jekyllrb.com/) - a static site generator. For our purposes it is used to combine multiple markdown files into a single markdown file.

## Pandoc
[Pandoc](http://pandoc.org/) - converts _from_ many file formats _to_ many other file formats. For our purposes, it converts our markdown file to epub and pdf.

## Kindlegen
[KindleGen](https://www.amazon.com/gp/feature.html?docId=1000765211) - Amazon's free tool to create .mobi/kindle files. For our purposes it converts epub to mobi.

## LaTeX / TexLive
[LaTeX](https://www.latex-project.org/) - typesetting software that can output PDF files.

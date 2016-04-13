---
layout: page
title: "WORKFLOW"
permalink: /documentation/workflow.html
--- 

## SHORT EXPLANATION

### new.sh
Creates the scaffolding required for each book.

### bind.sh
* Jekyll combines markdown files into a single file per format
* Pandoc the epub markdown files and coverts them to epub
* Kindlegen takes the Amazon epub and converts it to mobi
* Pandoc uses LaTeX to convert the pdf markdown files to pdf

        
## LONG EXPLANATION

### new.sh
Creates the scaffolding required for each book.

### bind.sh
* jekyll build
  * Jekyll looks inside Source
    * Any folder in Source that is not preceded by an underscore (_includes) is 'built'
  * Jekyll 'builds' everything inside Source/$BOOK-TITLE
    * Each file inside Source/$BOOK-TITLE simply tells Jekyll that we want that file built
    * The YAML front matter of a file tells Jekyll which layout to use when building the file
    * Jekyll looks for the layout and concatenates the individual files files defined inside that layout
    * Jekyll outputs the final result of each file into _site as an html file
* rename
  * changes the extension of all .html files in _site to .md (since that's what we want to input into Pandoc)
* Pandoc converts the markdown files to whatever formats we've told it to

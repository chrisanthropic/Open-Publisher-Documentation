---
layout: page
title: "USE"
permalink: /documentation/use.html
--- 

## Start a New Book
Use the `new.sh` script to create a new book. It creates everything needed and puts it in the right places so that you can just write.

Run the command `. new.sh` and enter the title of your book when prompted.

## Write Your Manuscript
Paste your manuscript in `Source/_includes/$BOOK-TITLE/chapters.md`

## Update Your MetaData
The beggining of your `Source/_includes/$BOOK-TITLE/chapters.md` contains "YAML Front Matter" and is used to define metadata about your book that we use in various places for various templates. Anything with an asterisk is optional.

```
---
title: Title of your book
subtitle*: Optional subtitle
author: Author Name
website: Author Website

type: Genre of your book
lang: A string value in BCP 47 format: http://tools.ietf.org/html/bcp47 (example: en-US)
date: YYYY-MM-DD
year: YYYY

cover-image: Source/images/YOUR-IMAGE.jpg

publisher: Publisher of your book
rights: A single sentence regarding the licensing of your book

isbn*: Optional ISBN of your print book
isbn-13*: Optional 13 digit ISBN of your print book
epub-isbn*: Optional ISBN of your epub

dedication: Optional dedication.

identifier:
    - scheme: UUID
      text: A unique UUID for your ebook.
      
contributors*:
    - designer*: Who designed your book/cover
      artist*: Who created the art of your book cover
      editor*: Who edited your book

book1*: 
    - title*: Optional books to include on the title page
      link*: If you include Amazon links here, they'll get linked in the Amazon version
book2*:
    - title*: Add a second book
      link*: http://www.amazon.com/dp/B0090NFRY2
book3*:
    - title*: This handles up to 5 books
      link*: http://www.amazon.com/dp/B00HE5I1BE
    
review*:
    - amazon*: https://www.amazon.com/review/create-review?asin=B007UIYEAW | Optional Amazon url to review your book.
    
magnet*:
    - image*: ../Images/file0.jpg | optional image/url to add to the front matter of your ebooks to get people to join your newsletter
      link*: https://www.backthatelfup.com/free-books/
---
```

## Customize Common Pages
Open-Publisher uses three 'common' pages by default which are shared between all books. These pages will need to be customized with your information.

Customize the contents of `Source/_includes/amazon_review.md`, `Source/_includes/bio.md`, and `Source/_includes/license.md`.

* **Amazon Review**: This page is used for our Amazon template and is added to the last page of the book immediately following the ending. We use it to kindly request that the reader consider leaving a review and provide a link to the Amazon page where they can easily do so.

* **Bio**: This page is used as a bio page for more information about the author.

* **License**: This is the license page. We default to the Creative Commons Attribution-NonCommercial-ShareAlike license because that's what we personally use. Feel free to modify it to your preferred license.
  * NOTE: Due to technological limitations the license page here IS NOT used when creating a print-ready PDF which uses it's own license page as defined in the LaTeX template at `Pandoc/templates/cs-5x8-pdf.latex` in the "Create a copyright page" block.

## Build Your Book
Use the `bind.sh` script to create your books by running `. bind.sh $FORMAT $TITLE`

### Build all formats of book titled "Example"
Run `. bind.sh all Example`

### Build epub format of book titled "Example"
Run `. bind.sh epub Example`

### Build amazon format of book titled "Example"
Run `. bind.sh amazon Example`

### Build smashwords format of book titled "Example"
Run `. bind.sh smashwords Example`

### Build a generic PDF format of book titled "Example"
Run `. bind.sh pdf Example`

### Build a print-ready pdf format of book titled "Example"
Run `.bind.sh print Example`

## Build Multiple Books
Open-Publisher can easily handle multiple books.

### Build ALL formats of ALL books
Run `. bind.sh all all`

### Build epub format of ALL books
Run `. bind.sh epub all`

### Build amazon format of ALL books
Run `. bind.sh amazon all`

### Build smashwords format of ALL books
Run `. bind.sh smashwords all`

### Build a generic PDF format of ALL books
Run `. bind.sh pdf all`

### Build a print-ready pdf format of ALL books
Run `.bind.sh print all`

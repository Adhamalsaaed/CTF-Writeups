# picoCTF — Secret of the Polyglot (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/423?page=1&category=4

## Steps
1) file flag2of2-final.pdf

=> flag2of2-final.pdf: PNG image data

2) strings & exiftool flag2of2-final.pdf

=> Nothing suspicious

3) xxd flag2of2-final.pdf | head

=> 00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR

4) pngcheck flag2of2-final.pdf

=> flag2of2-final.pdf  additional data after IEND chunk (very important)

5) how it is png and open like pdf

=> export file on hexeditor and search by Ctrl+F "IEND"

=> you will see "IEND<<Be%PDF"

=> IEND usually use to finish any image thats mean there are image in pdf

=> he finish it and add pdf after that >> that explain why it isnt open when you change extension from .pdf to png

6) copy the first HEXs byte before PDF and make an image with it

=> open image

=> picoCTF{f1u3n7_ "first part"

## Flag
picoCTF{f1u3n7_1n_pn9_&_pdf_7f9bccd1}

## What I Learned
- Polyglot files can be both PNG and PDF at the same time
- IEND marks the end of a PNG — any data after it is hidden content
- Always check magic bytes — file extensions can be misleading

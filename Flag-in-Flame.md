# picoCTF — Flag in Flame (Cylab)

## Challenge Link
https://learn.cylabacademy.org/library/523?page=1&category=4

## Steps

**1) file logs.txt**
=> ASCII text

**2) exiftool logs.txt**
=> Nothing suspicious

**3) xxd logs.txt | head -20**
=> 6956 424f 5277 304b 4767 6f41 4141 414e  iVBORw0KGgoAAAAN
=> "iVBORw0KGgo" is the magic bytes of a PNG image encoded in Base64

**4) base64 -d logs.txt > output.png**
=> Decoded Base64 to PNG image

**5) tesseract output.png output**
=> Extracted text from image:
7069636F4354467B666F72656E736963735F616E616C797369735F69735F616D617A696E675F65633139383466637D

**6) Decode Hex**
=> picoCTF{forensics_analysis_is_amazing_ec1984fc}

## Flag
picoCTF{forensics_analysis_is_amazing_ec1984fc}

## What I Learned
- How to identify Base64 encoded files using magic bytes (iVBORw0KGgo = PNG)
- How to decode Base64 to recover hidden image files
- How to extract text from images using tesseract OCR
- How to decode Hex encoding to readable text

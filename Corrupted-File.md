# picoCTF — Corrupted File (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/519?page=1&category=4

## Steps
file file
=> file: data

xxd file | head
=> 00000000: 5c78 ffe0 0010 4a46 4946 0001 0100 0001  \x....JFIF......
=> first tow bytes should be FF D8

open https://hexed.it/ import your file and edit first tow bytes
=> you will get image
=> flag in image

## Flag
picoCTF{r3st0r1ng_th3_by73s_684e09bc}

## What I Learned
- JPEG magic bytes are FF D8 — corrupted files can be fixed manually using a hex editor
- Always check magic bytes when file command returns unknown data

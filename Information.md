# picoCTF — Information (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/186?page=2&category=4

## Steps
file cat.jpg
=> cat.jpg: JPEG image data

exiftool cat.jpg
=> License: cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9

echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 -d

=> picoCTF{the_m3tadata_1s_modified}

## Flag
picoCTF{the_m3tadata_1s_modified}

## What I Learned
- Metadata fields like License can contain hidden encoded flags
- exiftool is essential for any image forensics challenge

# picoCTF — RED (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library?page=1&category=4

## Steps
1) file red.png

=> red.png: PNG image data

2) exiftool red.png && strings red.png

=> Nothing suspicious

3) zsteg red.png

=> cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==

4) decode base64

=> picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}

## Flag
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}

## What I Learned
- zsteg is powerful for detecting hidden data in PNG files
- When file and exiftool return nothing always try zsteg on PNG files

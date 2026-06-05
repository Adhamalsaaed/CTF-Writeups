# picoCTF — Timeline 0 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/720?page=2&category=4

## Steps
1) gunzip partition4.img.gz
=> partition4.img

2) fls -r -m / partition4.img > my_time.txt

3) mactime -b my_time.txt -d > final_timeline.csv

4) icat partition4.img 4945
5) 
=> NzFtMzExbjNfMHU3MTEzcl9oM3JfNDNhMmU3YWYK

6) echo "NzFtMzExbjNfMHU3MTEzcl9oM3JfNDNhMmU3YWYK" | base64 -d

=> 71m311n3_0u7113r_h3r_43a2e7af

## Flag
picoCTF{71m311n3_0u7113r_h3r_43a2e7af}

## What I Learned
- MAC timelines help identify suspicious files by their timestamps
- icat extracts file content directly from disk images using inode number

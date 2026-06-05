# picoCTF — Timeline 0 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/720?page=2&category=4

## Steps
gunzip partition4.img.gz
=> partition4.img

fls -r -m / partition4.img > my_time.txt

mactime -b my_time.txt -d > final_timeline.csv

icat partition4.img 4945
=> NzFtMzExbjNfMHU3MTEzcl9oM3JfNDNhMmU3YWYK

echo "NzFtMzExbjNfMHU3MTEzcl9oM3JfNDNhMmU3YWYK" | base64 -d
=> 71m311n3_0u7113r_h3r_43a2e7af

## Flag
picoCTF{71m311n3_0u7113r_h3r_43a2e7af}

## What I Learned
- MAC timelines help identify suspicious files by their timestamps
- icat extracts file content directly from disk images using inode number

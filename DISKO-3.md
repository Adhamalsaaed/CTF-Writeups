# picoCTF — DISKO 3 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/507?page=2&category=4

## Steps
1) gunzip disko-3.dd.gz

2) fdisk -l disko-3.dd

=> Disk disko-3.dd: 100 MiB, 104857600 bytes, 204800 sectors

=> Disk identifier: 0x00000000 — It is a partition

3) fls -a disko-3.dd

=> d/d 4: log — seems suspicious

=> v/v 3225859: $MBR

=> v/v 3225860: $FAT1

=> v/v 3225861: $FAT2

=> V/V 3225862: $OrphanFiles

4) fls -a disko-3.dd 4

=> you will see many things in output and you will notice a file

=> r/r 522628: flag.gz and others (r -> regular "File")

5) icat disko-3.dd 522628 > file

6) gunzip file
=> file.txt

7) cat file

=> Here is your flag

=> picoCTF{n3v3r_z1p_2_h1d3_26d4f233}

## Flag
picoCTF{n3v3r_z1p_2_h1d3_26d4f233}

## What I Learned
- fls -a shows all files including hidden system files
- Suspicious directories like log are always worth investigating
- Files can be compressed inside disk partitions using gzip

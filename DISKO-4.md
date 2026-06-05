# picoCTF — DISKO 4 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/704?page=2&category=4

## Steps
1) gunzip disko-4.dd.gz

2) fdisk -l disko-4.dd

=> Disk disko-4.dd: 100 MiB, 104857600 bytes, 204800 sectors

=> Disk identifier: 0x00000000 — It is a partition

3) fls -a disko-4.dd

=> d/d 4: log — seems suspicious

=> v/v 3225859: $MBR

=> v/v 3225860: $FAT1

=> v/v 3225861: $FAT2

=> V/V 3225862: $OrphanFiles

4) fls -a disko-4.dd 4

=> * num means this is a deleted file

=> r/r * 522629: messages

=> r/r * 532021: dont-delete.gz (SOS)

5) icat disko-4.dd 532021 > file.gz

6) gunzip file.gz

7) cat file

=> Here is your flag

=> picoCTF{d3l_d0n7_h1d3_w3ll_4fed4369}

## Flag
picoCTF{d3l_d0n7_h1d3_w3ll_4fed4369}

## What I Learned
- Deleted files in FAT32 are marked with * in fls output but data still exists
- icat recovers deleted files using their inode number
- Never trust deletion — forensics tools can always recover deleted files

# picoCTF — DISKO 2 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/506?page=2&category=4

## Steps
1) gunzip disko-2.dd.gz

2) fdisk -l disko-2.dd

=> Units: sectors of 1 * 512 = 512 bytes

=> disko-2.dd1       2048  53247   51200  25M 83 Linux

=> disko-2.dd2      53248 118783   65536  32M  b W95 FAT32

3) dd if=disko-2.dd of=linuxdisko.img skip=2048 bs=512 count=51200

4) strings linuxdisko.img | grep "picoCTF"
=> picoCTF{4_P4Rt_1t_i5_a93c3ba0}

## Flag
picoCTF{4_P4Rt_1t_i5_a93c3ba0}

## What I Learned
- dd can extract specific partitions from disk images using skip and count
- Always analyse each partition separately when fdisk shows multiple partitions

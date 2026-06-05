# picoCTF — DISKO 1 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/505?page=1&category=4

## Steps
1) gunzip disko-1.dd.gz

=> disko-1.dd

2) file disko-1.dd

=> FAT (32 bit)

3) strings disko-1.dd | grep "pico"

=> picoCTF{1t5_ju5t_4_5tr1n9_e3408eef}

## Flag
picoCTF{1t5_ju5t_4_5tr1n9_e3408eef}

## What I Learned
- strings command can extract hidden text directly from disk images
- FAT32 disk images can be analysed without mounting

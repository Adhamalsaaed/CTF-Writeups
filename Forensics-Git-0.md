# picoCTF — Forensics Git 0 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/705?page=2&category=4

## Steps
gunzip disk.img.gz

file disk.img
=> disk.img: DOS/MBR boot sector

mkdir -p mnt/file/

fdisk -l disk.img
=> Sector size (logical/physical): 512 bytes / 512 bytes
=> disk.img3       1140736 2097151  956416  467M 83 Linux

sudo mount -o loop,offset=$((1140736 * 512)) disk.img mnt/file/

find mnt/file/ -name ".git" 2>/dev/null
=> mnt/file/home/ctf-player/Code/secrets/.git

cd mnt/file/home/ctf-player/Code/secrets && ls
=> note.txt

cat note.txt
=> The picoCTF flag format is 'picoCTF{}' where there is some leetspeak phrase in between the curly braces

git log --oneline
=> 327681b (HEAD -> master) Wrap this phrase in the flag format: g17_1n_7h3_d15k_041217d8

## Flag
picoCTF{g17_1n_7h3_d15k_041217d8}

## What I Learned
- Disk images can contain git repositories with hidden flags
- Always mount disk partitions using the correct offset from fdisk
- git log shows commit history which can contain flag hints

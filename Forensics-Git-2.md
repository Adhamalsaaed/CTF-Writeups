# picoCTF — Forensics Git 2 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/707?page=2&category=4

## Steps
1) gunzip disk.img.gz

2) fdisk -l disk.img

=> Sector size (logical/physical): 512 bytes / 512 bytes

=> disk.img3       1140736 2097151  956416  467M 83 Linux

3) mkdir -p mnt/fileimg/

4) sudo mount -o loop,offset=$((1140736 * 512)) disk.img mnt/fileimg/
=> "start in" is the sector you should times it with 512 , because mount read bytes

5) find mnt/fileimg/ -name ".git" -type d
=> mnt/fileimg/home/ctf-player/Code/killer-chat-app/.git

6) git log
=> fatal: your current branch 'master' does not have any commits yet

7) git status

=> new file: logs/1.txt

=> new file: logs/2.txt

=> new file: logs/4.txt

=> file 3.txt not there

8) git cat-file --batch-all-objects --batch-check
=> commits = (Snapshots) , trees = (Folders) , blobs = (file content) flag in this

9) git cat-file --batch-all-objects --batch | strings | grep "pico"
=> Jay: Ask Rusty at the door and use password picoCTF{g17_r35cu3_16ac6bf3}

## Flag
picoCTF{g17_r35cu3_16ac6bf3}

## What I Learned
- Even without commits git objects still store staged file content
- git cat-file --batch-all-objects reveals all hidden objects in the repo
- Missing files in git status is always suspicious

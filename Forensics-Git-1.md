# picoCTF — Forensics Git 1 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/706?page=2&category=4

## Steps
1) gunzip disk.img.gz

2) file disk.img
=> disk.img: DOS/MBR boot sector

3) mkdir -p mnt/disk/

4) fdisk -l disk.img
=> Sector size (logical/physical): 512 bytes / 512 bytes
=> disk.img3       1140736 2097151  956416  467M 83 Linux

5) sudo mount -o loop,offset=$((1140736 * 512)) disk.img mnt/disk/
=> now we have the img disk

6) find mnt/disk/ -name ".git"
=> mnt/disk/home/ctf-player/Code/secrets/.git

7) cd mnt/disk/home/ctf-player/Code/secrets

8) git log
=> commit 5fb8194539c770a830b8ba089a50778c07072b03 (HEAD -> master) — Remove flag
=> commit 177789af0b300e043ea8f54ea57d6cee352291ae — Add flag

9) git status
=> On branch master — nothing to commit, working tree clean

10) git cat-file --batch-all-objects --batch-check
=> commits = (Snapshots) , trees = (Folders) , blobs = (file content) flag in this

11) git cat-file --batch-all-objects --batch | strings | grep "CTF"
=> picoCTF{g17_r3m3mb3r5_d4ddf904}

another solve:
git show 177789af0b300e043ea8f54ea57d6cee352291ae
=> diff --git a/flag.txt b/flag.txt
=> +picoCTF{g17_r3m3mb3r5_d4ddf904}

## Flag
picoCTF{g17_r3m3mb3r5_d4ddf904}

## What I Learned
- Git never truly deletes data — deleted files still exist in old commits
- git cat-file --batch-all-objects shows all objects including deleted ones
- git show on old commit hash recovers deleted file content

# picoCTF — Timeline 1 (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/721?page=2&category=4

## Steps
gunzip

fls -r -m / partition4.img > my_time.txt
=> Create a Sleuthkit MAC timeline

mactime -b my_time.txt -d > final_timeline.csv
=> create timestamps

open final_timeline.csv

filter type with macb
=> which means this file is new without any edit

scroll down you will see /root/.ash_history
=> thats is impossible in normal because system created this file in start
=> thats mean it is made by user

you will notice 32716|/etc/chat
=> actually chat it isnt normal file in etc/ that is suspicious

icat partition4.img 32716
=> NTczNDE3aDEzcl83aDRuXzdoM18xNDU3XzU4NTI3YmIyMjIK

echo "NTczNDE3aDEzcl83aDRuXzdoM18xNDU3XzU4NTI3YmIyMjIK" | base64 -d
=> 573417h13r_7h4n_7h3_1457_58527bb222

## Flag
picoCTF{573417h13r_7h4n_7h3_1457_58527bb222}

## What I Learned
- MAC timelines help detect suspicious file activity on disk images
- Unusual files in system directories like /etc are always suspicious
- icat extracts file content directly from disk images using inode number

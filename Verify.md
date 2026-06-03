# picoCTF — Verify (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/450?page=1&category=4

## Steps
ssh -p 58146 ctf-player@rhea.picoctf.net

ls
=> checksum.txt  decrypt.sh  files

sha256sum files/* | grep "3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4"

=> 3ad37ed6c5ab81d31e4c94ae611e0adf2e9e3e6bee55804ebc7f386283e366a4  files/e018b574

./decrypt.sh files/e018b574
=> picoCTF{trust_but_verify_e018b574}

## Flag
picoCTF{trust_but_verify_e018b574}

## What I Learned
- SHA256 is used to verify file integrity — even one byte change gives a completely different hash
- Always verify file checksums before trusting a file

# picoCTF — Riddle Register

## Challenge Link
https://learn.cylabacademy.org/library/698?page=1&category=4

## Steps

**1) Read the PDF**
=> Nothing suspicious

**2) file riddle.pdf**
=> PDF document

**3) exiftool riddle.pdf**
=> Author: cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jOTk5ZTJhNH0=

**4) Decode base64**
=> echo "cGljb0NURntwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV9jOTk5ZTJhNH0=" | base64 -d

## Flag
picoCTF{puzzl3d_m3tadata_f0und!_c999e2a4}

## What I Learned
- Flags can be hidden in file metadata not just content
- How to extract metadata using exiftool
- How to identify and decode Base64 encoding

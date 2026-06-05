
# picoCTF — CanYouSee (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/408?page=1&category=4

## Steps
unzip

exiftool ukn_reality.jpg

=> Attribution URL: cGljb0NURntNRTc0RDQ3QV9ISUREM05fZDhjMzgxZmR9Cg==

echo "cGljb0NURntNRTc0RDQ3QV9ISUREM05fZDhjMzgxZmR9Cg==" | base64 -d

=> picoCTF{ME74D47A_HIDD3N_d8c381fd}

## Flag
picoCTF{ME74D47A_HIDD3N_d8c381fd}

## What I Learned
- Flags can be hidden in metadata fields like Attribution URL
- Always check all exiftool fields not just the common ones

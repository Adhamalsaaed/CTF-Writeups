# cylabCTF — Hidden in Plainsight

## Challenge Link
https://learn.cylabacademy.org/library/524?page=1&category=4

## Steps

**1) file img.jpg**
=> JPEG image data, comment: "c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9"

**2) echo "c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9" | base64 -d**
=> steghide:cEF6endvcmQ=

**3) echo "cEF6endvcmQ=" | base64 -d**
=> pAzzword (steghide password found)

**4) steghide extract -sf img.jpg -p pAzzword**
=> wrote extracted data to "flag.txt"

**5) cat flag.txt**
=> picoCTF{h1dd3n_1n_1m4g3_54e31417}

## Flag
picoCTF{h1dd3n_1n_1m4g3_54e31417}

## What I Learned
- Flags can be hidden in image comments (metadata)
- How to decode double Base64 encoding
- How to extract hidden files using steghide with a password

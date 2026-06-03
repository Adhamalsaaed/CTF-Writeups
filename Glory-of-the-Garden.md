# picoCTF — Glory of the Garden (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/44?page=2&category=4

## Steps
file garden.jpg
=> garden.jpg: JPEG image data

exiftool garden.jpg
=> Red Tone Reproduction Curve: (Binary data 2060 bytes, use -b option to extract)
=> Green Tone Reproduction Curve: (Binary data 2060 bytes, use -b option to extract)
=> Blue Tone Reproduction Curve: (Binary data 2060 bytes, use -b option to extract)

strings garden.jpg | grep "pico"
=> picoCTF{more_than_m33ts_the_3y339140129}

## Flag
picoCTF{more_than_m33ts_the_3y339140129}

## What I Learned
- always keep basics when i saw the result of exiftool i was thinking in lsb but it was not
- Never skip strings — sometimes the flag is hiding in plain sight

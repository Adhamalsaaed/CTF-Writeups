# picoCTF — Rogue Tower (Cylab)
## Challenge Link
https://learn.cylabacademy.org/library/714?page=2&category=4

## Steps
open file in wireshark

analyse Packets

from the first see , there are suspicious external ip (198.51.100.243) try to Get data by requesting local network IPs

you will see a GET request and after it 6 POST request
i usually check POSTs request , because they have data.

if you see any POST request and watch in HTTP Stream
you will see data it is seems encoding in base64

collect them
=> Q15TWnpifkxBB1dACmlbBF9bb0EJQQtFbAQBBQ1QXAEASg==

decode in CyberChef
=> C^SZzb~LAW@i[_[oA AElP\J
=> it needs decryption

HINT 3 => The encryption key is derived from the victim device's IMSI

victim device's IMSI , which is the suspicious ip (198.51.100.243)
you can get it from GET api register request
=> IMSI:310410337059687

try decode Q15TWnpifkxBB1dACmlbBF9bb0EJQQtFbAQBBQ1QXAEASg== with XOR key in CyberChef (type UTF8)

try to delete numbers from the key one by one until you get correct output

when you reach 37059687
=> picoCTF{r0gu3_c3ll_t0w3r_3104fd63}

## Flag
picoCTF{r0gu3_c3ll_t0w3r_3104fd63}

## What I Learned
- Always check POST requests in Wireshark — they contain data
- XOR encryption key can be found in network traffic metadata like IMSI
- CyberChef is powerful for trying different decryption keys

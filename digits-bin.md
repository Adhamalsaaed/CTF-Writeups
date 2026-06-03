# picoCTF — digits.bin | Binary to Image (Cylab)

## CTF Link
https://learn.cylabacademy.org/library/698?page=1&category=4

## Steps

**1) file digits.bin**
=> ASCII

**2) strings digits.bin | head -20**
=> 0 and 1 (binary as expected)

**3) wc -c digits.bin**
=> 71192 bits (useful to know encoding by 71192/8 = 8899 byte = 8.7KB which is image size)

**4) python3 -c "data=open('digits.bin').read().strip(); print(''.join([chr(int(data[i:i+8],2)) for i in range(0,len(data),8)]))"**
=> to decode you will see 'ÿØÿàJFIFÿÛC' in head which is meaning this is a image

**5) python3 -c "data=open('digits.bin').read().strip(); open('output.jpg','wb').write(bytes([int(data[i:i+8],2) for i in range(0,len(data),8)]))"**
=> convert to image

**6) eog output.jpg**
=> flag is 'picoCTF{h1dd3n_1n_th3_b1n4ry_67bd9b59}'

## What I Learned
- How to detect binary file encoding
- How to decode binary encoding by Python
- Read and analyse decoded binary data (file signatures)

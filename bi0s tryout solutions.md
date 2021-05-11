# bi0s Tryouts

### Multi Encoder
- From the file enc.py we can see that the flag is encoded to base64 then to hex 5 times in a loop
- To get the flag from the cipher text provided we need to do just the reverse
- This can be achieved using the functions `binascii.unhexlify(flag)` and `base64.b64decode(flag)` from the libraries `binascii` and `base64`
- The flag: `inctfj{Y0u_@re_Qu1t3_th3_D3c0d3r}`

### base-base-base
- The given cipher text has been encrypted 3 times with `base16(hexadecimal)` -> `base32` -> `base64`
- Decode it backwards and you will get the flag `inctfj{b4s3s_4r3_c00000000l}`

### Single byte X0r
- We are given a cipher text that has been xored against a single character `z`
- To get the flag we just need to xor it again with the same key
- Flag: `inctfj{x0r_c4n't_b3_e4sily_br0k3n}` 

### Naïve Cipher
- We are given a ciphertext that has been shifted up or down the alphabet with a certain key
- We can figure out the key by finding out the difference between the original flag as we already know the flag format `inctfj{}`
- Key: `-5` \ flag: `inctfj{thee_the_master_of_caeser_cipher}`

### Angry Steve
- We are given a jpg with some text hidden inside it.
- Any printable 

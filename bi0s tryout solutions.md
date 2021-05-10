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
- We are given an xor encoded cipher text 

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
- We are given a jpg with some text hidden inside it
- We can use the strings command in terminal to extract text from files
- Flag: `inctfj{string5_m4keth_fl4gs}`

### Mischief Kid
- We are given a zip file with a jpg inside it
- Upon checking the hex data of the image we can see that there are embedded files in it
- We can use a tool like `Binwalk` to get the position of the embedded data and `dd` tool to extract it which gives us two files `busted.png` and `flag.txt`
- When you look at the hex data of the two files we can see that both files have the PNG file signature but `busted` is missing some magic numbers and `flag` has the wrong format of `.txt`
- Fixing the format of `flag` to `.png` gives us an image but it doesn't have the flag in it. Using the hex data of `flag` as reference insert the missing magic numbers to fix `busted` which will give us the image containing the flag

![busted](https://user-images.githubusercontent.com/71893695/117829306-43f38680-b290-11eb-90fb-6b6a5e0d9c5f.png)
- Flag: `inctfj{_4Ye_@aRr4mbB4_u_g0T_m3!}`

### Snow Man
- We are given a text file with flag hidden inside. From the title we can guess that this has been done by `Stegsnow` which is a tool that uses `Whitespace Steganography`
- Upon looking at through the text file, we can see the line `the password is thisiseasy` which gives us the password for the encryption
- By using the `Stegsnow` tool to decode, we get a base64 encoded string:`aW5jdGZqe2g0aDRfc3QzZ3NuMHdfaTVfYzAwMDAwMDAxfQ==`
- Decoding the bas64, we get: `inctfj{h4h4_st3gsn0w_i5_c00000001}`

### Con-The-Cat
- We are given a PNG file, which upon checking the hex data we can see multiple file signatures after the PNG
- The file signatures are of JPG, so searching for the beginning flag `FF  D8` and ending flag`FF D9` show us that all of them are complete jpg files
- By using a tool like `Ghex` or `HxD Editor`, we can select the data and save them to a new file with jpg format which will give us the image with the flag

![image1](https://user-images.githubusercontent.com/71893695/117829498-71403480-b290-11eb-8618-1593cb86ce2a.jpg)
- Flag: `inctfj{y0u_c4nt_s33_m3!!!}`

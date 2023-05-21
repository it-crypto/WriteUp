Level 0

Q. The following string encodes the password using Base64:

S1JZUFRPTklTR1JFQVQ=

Ans : KRYPTONISGREAT

//used cyberchef

![image](https://github.com/it-crypto/WriteUp/assets/54020728/c6bfa8e8-65f1-4ea7-a342-4bcc5bfb5647)

Level 1

Q. From the krypton folder, read the readme file and do required. Use rot13 cipher to get the password.

Ans: ROTTEN

![image](https://github.com/it-crypto/WriteUp/assets/54020728/434f655e-f159-4689-ac12-bcd54f8d13d8)

Level 2:

Q. Caesar Cipher

Ans: CAESARISEASY

![image](https://github.com/it-crypto/WriteUp/assets/54020728/73e01f33-c9d5-45f3-8cda-f3b45d16358a)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/f3d9ce92-fc04-4806-a1af-51dcae4da346)


Level 3:

Q. Frequency Analysis

→ In this level, we need to find frequencies of the letters from found files and find which letter is suited to which.
→ We can find single frequencies, double frequencies and tripe frequencies and work on that.
→ After finding out the suitable letter replace them and make substitutions and get the key.
→ After that use the “tr” command to get the plain text from krypton4

Command: cat krypton4 | tr ABCDEFGHIJKLMNOPQRSTUVWXYZ BOIHGKNQVTWYURXZAJEMSLDFPC

Ans: BRUTE

![image](https://github.com/it-crypto/WriteUp/assets/54020728/55e31fcd-b961-4ab0-a1eb-2fec658b747e)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/dc69e7f2-55ea-4725-8b5f-353f9a533db0)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/5ea871d1-f368-456c-a563-63fc6a513599)
 

Level4

Q. find the password

→ In this level, we learn about Vigenere cipher, the cipher where we use different substitutions cipher (polyalphabetic cipher). Some times, we are provided with key length or keyword based on that we can find the which letter is being mapped to which letter and then find the letter and use the key to find the decrypted text.
→ In this level, we used this website we can find the keyword based on the key length and used that to find the decrypted text.

Ans: CLEARTEXT

https://f00l.de/hacking/vigenere.php

![image](https://github.com/it-crypto/WriteUp/assets/54020728/989b1ea8-f50b-4091-8ac4-0b41d1921d50)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/a84491bf-1293-43cc-a806-e7ffe6122ddb)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/de4344b8-290b-4c89-8e7a-b7af6f12d02e)


Level 5:

→ In this level also, we have a vignere cipher but without any key or key length.
→ We need to find out what is the key.
→ I used the tool https://www.dcode.fr/vigenere-cipher to find the key.
→ With the key found, I took the cipher text and used then decryted the text.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/362031d5-5a3e-40ff-9f9c-e30236b23d0f)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/b7405dd5-029b-4fd4-99a2-f7b2cf8e2c63)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/4f5a6638-39ff-4c15-9b4e-1a309a9794cf)

Level 6:

→ In this level, we are given a stream cipher.
→ We need to find the key and then use the key on the cipher text to get the plain text.
→ We are given an executable which takes two arguments one is input file and other is output file.
→ We have given a sample data to find what is the pattern.
→ We find that for every 30 characters the pattern is repeating.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/1e0936b0-4bab-4e87-9c02-7fd2b0ba9c7b)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/06187f97-7d41-4c61-9997-e103c112d498)

→ So used this as key and have taken the cipher text and written a script to find the password.

Code:

key = 'EICTDGYIYZKTHNSIRFXYCPFUEOCKRN'
ciphertext='PNUKLYLWRQKGKBE'

for i in range(len(ciphertext)):
        k = ord(ciphertext[i])-ord(key[i])
        if k<0: k+=26
        k += ord('A')
        print(chr(k),end='')

Ans: LFSRISNOTRANDOM

![image](https://github.com/it-crypto/WriteUp/assets/54020728/b9f25076-1893-4d59-95af-0caf39e00bf6)


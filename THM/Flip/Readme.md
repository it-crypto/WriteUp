# Flip

* In this room, we will be learning about AES CBC bit flipping attack.
* AES : Advanced Encryption Standard
* The AES Encryption algorithm (also known as the Rijndael algorithm) is a symmetric block cipher algorithm with a block/chunk size of 128 bits. It converts these 
    individual blocks using keys of 128, 192, and 256 bits. Once it encrypts these blocks, it joins them together to form the ciphertext.
* CBC : Cipher Block Chaining method.
* Cipher block chaining (CBC) is a mode of operation for a block cipher -- one in which a sequence of bits are encrypted as a single unit, or block, with a cipher 
   key applied to the entire block. Cipher block chaining uses what is known as an initialization vector (IV) of a certain length.
* In the current room, we are provided with the python file where how the encryption and decryption takes place and how we can get the flag.
* We need to use netcat to connect to the IP and port mentioned, it will ask for the credentials we can see from the file credentials are given.
  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/aa44982c-e351-4996-8f6e-e6e9682cef7e)

* If we try with the credentials mentioned, we wont be able to get the flag.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/c838e309-c3f8-4076-9c6e-309a26681032)

* From the file, we can see that the by giving the same credentials we wont be able to login 
  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/6a320c9f-96cb-4421-8b24-380120a65df8)

  but at the same time we need to give the same credentials so that we can retrieve the required check from which we can get the flag.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/13c89412-2311-403f-838a-104fba17f091)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/bff263b9-48f7-4986-a628-36c7ac4461a3)

* Lets try by changing the credentials, and see what will happen.  
  
  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/2b8d04ba-cfa0-4639-af7c-81311739d692)

* From AES Encryption and Decryption process we can see that the we can perform XOR operation we can know the either two of the text we want to xor with to get 
   the third text.

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/51586f8d-6694-4d39-89fb-b607cec28eac)

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/ae291745-33c9-4572-b44f-ecbbcdf18bfa)

* From the cipher text we got, we will perform some operations on the previous block so that the the credential we changed will be reverted back to the original 
  one and get the cipher text correctly which matches with the condition to get the flag.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/0ef7a7a7-82f0-4c99-8a50-b68a30ed4ee7)

* We have found the length of the message that is used for encrypting, it is 41 in length for remaining characters padding will be added to get the reult 
    properly.
* The cipher text length is 96 which is half of the block.
* Now we will try to find the first block of data, which will be 'acess_username='
    
     ![image](https://github.com/it-crypto/WriteUp/assets/54020728/6d1e61b1-f6b8-43a3-a57a-592c4192c2ca)

*  Now we got two values of XOR, we need to perform XOR to get the third one.
  
   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/64e4b2e1-5ac5-4a49-949d-0ae9f18b2bb3)

* We got the XOR value of the decrypted text and we are equating with 'b' as we have changed the username credential from 'admin' to 'bdmin'
* Now we need to change back to 'a' and with the resulted text we need to replace the cipher text.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/07549546-039e-4f79-aaf6-b1026ffa565e)
  
* If we can see we are changing the only first two bits of the cipher text, while remaining are same.
* After entering the cipher text we will get the flag.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/0517d990-76ee-44ef-b6a8-94a584f1b831)

* Flag:  
 ![image](https://github.com/it-crypto/WriteUp/assets/54020728/9256f176-f47b-499e-97f1-2e964bbc8c51)

* References:
  * https://www.youtube.com/watch?v=QG-z0r9afIs&ab_channel=decrypt
  * https://zhangzeyu2001.medium.com/attacking-cbc-mode-bit-flipping-7e0a1c185511



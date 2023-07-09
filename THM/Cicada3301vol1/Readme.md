# Cicada3301vol1

* In this room we will explore the basic steganography and cryptography challenges.
* From the downloaded files we got one sound file and one image file.

# Task 1

* First lets start with sound file, we will be using sonic visualiser tool to explore the file and find anything interesting from the file.
* I have tried different options to see if there is any different I can find, finally when clicking on "add Spectogram" I am able to find the QR code.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/400a9ea8-01c4-45c8-92eb-779f39e43467)

* On scanning the QR code, I got pastebink link which contains the passphrase and key.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/e68c2e29-c67b-44c3-9e5f-80f9b22f6c5c)

# Task 2

* Perform base 64 decode on the found passphrase and key and get the decrypted one.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/d034dd25-31be-411e-a59f-7716e6ba6e14)

* From the hint provided, we knew that we have to use French Diplomat Cipher (Vignere Cipher) to encrpt the decypted passphrase with the decrypted key and get
   the final passphrase.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/42b1d20c-c63b-40de-9e31-c12e266597e5)

# Task 3

* When trying to extract any secret message data from the image file using stegtool (steghide) it prompted for the passphrase, so we can use the final passphrase
   we got from the previous task.
  
  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/c8eafa42-67ae-46fa-b443-bce73a3128ce)

* We got a text file from the image and the file contain the link. lets explore the link and find what it have.

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/4ab19a40-2138-49a2-8a77-9d2fc6a00a28)

# Task 4 

* From the link we got a image file, when trying steghide it didnt work.

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/826eb543-236f-4251-9360-e5ea59935dd0)

* From the hint provided and after searching for a while came across the tool **outguess**. Explored the options and tried using the tool on the image.

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/ef767597-9373-42e7-80f0-84696a90f5ad)

* When trying to input the image file, got error that "unknown type" so changed the file extension to jpg and tried it worked.
  
   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/d9ca64ce-aa36-431b-ab54-697fd993b804)

* From the output file we found a hash and some hint data how to proceed further.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/5e48f49e-aade-4982-b9a3-fda0dea444fa)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/c343d5d9-16f0-40e0-a7a8-5d335058b1dc)

# Task 5

* From the hash found in the previous task, identified it as SHA512, so used online site to decode the hash and found a link

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/4c855865-dad9-49ab-a61a-3333076850ab)

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/26bd44c9-2f06-4922-9c48-00c2f81e0525)

* From the hint we knew that we need to use the below data and check in the book which we got from the pastebink link that we got after decrypting the hash.

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/71c9e945-81b0-4438-8a93-8308325c8669)

* For positive integers we need to go forward in the text use negative integers to go backwards in the text, by doing so we got the tiny url.

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/d48d40f6-9bd6-4eb0-a72c-84ada05fde75)

# Task 6

* After decrypting the message found the tiny url which is redirecting to the original website which contains song.

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/d48d40f6-9bd6-4eb0-a72c-84ada05fde75)
  
   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/a38d27a7-31bc-459b-a94f-1d7de1f8794e)
  
  
  
  

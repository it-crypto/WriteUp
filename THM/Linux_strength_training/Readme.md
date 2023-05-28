# Level 1:

* Read the file named 'ReadMeIfStuck.txt'. What is the Flag?

![image](https://github.com/it-crypto/WriteUp/assets/54020728/a8d9485e-b8b7-4e39-959d-10f395337c31)

* Use the less command : which is used for finding the text in the long lines.
* After executing the command, type “/” and enter the word : hint is the fifth word is “{“
* so I searched for the “flag{“

![image](https://github.com/it-crypto/WriteUp/assets/54020728/8effa630-4fbd-498c-b91a-eca36e2cce41)

# Level 2:
* Find a file named readME_hint.txt inside topson's directory and read it. Using the instructions it gives you, get the second flag.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/4bec9337-8882-42e3-ae2a-44fa5888e6ec)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/d904deeb-5e17-42d3-883c-df35bb6075c8)

# Level 3:

* Find a wordlist  with the file extention of '.mnf' and use it to crack the hash with the filename hashC.txt. What is the password?

![image](https://github.com/it-crypto/WriteUp/assets/54020728/3938af9c-312e-4db7-91d8-1a626b57ae80)

* HashC.txt : c05e35377b5a31f428ccda9724a9dfbd0c5d71dccac691228d803c78e2e8da29

* I need to find what type of  hash it is. I checked and found one website and tried to see what hash it is. It says “SHA-256”.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/1ec1194c-9775-48ae-a492-83c5b9f54bc4)

* As the file is in remote ssh, I need to copy the file to local system. For that purpose I used scp.

* Command: scp sarah@10.10.232.1543:/home/sarah/’system AB’/db/ww.mf wordlist
* Here wordlist is the file where all the contents of ww.mnf will be stored.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/aca7a7fa-1984-4545-852f-63f145f3a1be)

* Now I am using john to get the password from the hashC.txt file using wordlist 

![image](https://github.com/it-crypto/WriteUp/assets/54020728/1222dcdd-7a7a-4929-90e6-a18e7574eb3c)

# Level 4:

* find a file called encoded.txt. What is the special answer?

* The file encoded.txt is of long lines. We can use less command to search for the answer.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/924b33e9-41a9-4837-9bee-1c4bbd7cf3d5)

* But before finding the keyword ‘special’ the file is encoded in base64. We need to decode it and save it in  a file and search for the keyword ‘special’ in the newly created file.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/6efabd54-574c-4422-a40b-54acba3b622b)

* When we find the word ‘special’ it says to find the file ent.txt. I found the file and it has hash. I used web and found the answer is ‘john’.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/23069d92-ca39-4d90-9f56-47ed25a0adb5)

Hash : bfddc35c8f9c989545119988f79ccc77

![image](https://github.com/it-crypto/WriteUp/assets/54020728/fabfd58d-e395-4e77-9f2a-b13e6b216e1c)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/304d4b47-df24-49ea-8ead-8b5569e52080)

# Level 5:

* Find an encrypted file called layer4.txt, its password is bob. Use this to locate the flag. What is the flag?

* All the files are of format AES symmetrically. Use the command : gpg filename. If it asks for passphrase just give the passphrase given and enter.

* One of the file is base64 decoded. I took the hash and searched in the https://hashes.com/en/tools/hash_identifier. But in the machine I used base64 command to decode it and created new file to copy the decoded base64 file.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/3aef86b8-069d-4b9c-a7c2-a77612a03a0f)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/41716cde-9c84-456c-946b-28ed36de962a)

# Level 6:

* Find the flag

![image](https://github.com/it-crypto/WriteUp/assets/54020728/6566b4e4-af3c-4df6-bf08-df45f97a10cb)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/b8a54ae9-30f4-45bf-98f4-b1606e55fda7)

* I am using the john the ripper tto extract the passphrase for the personal.txt.gpg hash. It takes time, the wordlist needs to be tac (tac reverse of cat – reveres the list)
passphrase : valamanezivonia

* Then I used the command ; gpg --decrypt personal.txt.gpg

![image](https://github.com/it-crypto/WriteUp/assets/54020728/a581346d-80bd-43f2-90c8-f7a91c403b9e)

# Level 7:

* Find a file called employees.sql and read the SQL database. (Sarah and Sameer can log both into mysql using the password: password). Find the flag contained in one of the tables. What is the flag?

This is full of database commands.

Command: Select * from employees where first_name=”Lobel”;

![image](https://github.com/it-crypto/WriteUp/assets/54020728/96042bb6-bfd8-429d-a321-b07cc782054a)


# Level 8:

* What is Sameer's SSH password?

![image](https://github.com/it-crypto/WriteUp/assets/54020728/c65d98ff-1b65-4975-b845-280ffa2af4ce)

Password : thegreatestpasswordever000

* What is the password for the sql database back-up copy ?

![image](https://github.com/it-crypto/WriteUp/assets/54020728/50eebfaf-db62-48e4-851b-eb3da0107f5b)

* But when I tried to decrypt the copy with the given password, it is failing. 
* Then I referred to the above  chat log, in that it described the password is chosen from the conf directory of file 50mb which had the wordlist directory location from which password is chosen.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/146fd5ba-cb04-4dab-b279-3b4c5413ffde)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/77fd390c-b5aa-4464-b44d-29820a61a57b)

* I used grep to find the word “ebq” it is found in three files. I used cat command to combine three files  into the single file.
Command  :  cat file1 file2 file3  > wordlist (file1:pLmjwi file2:LmqAQl file3:Ulpsmt).
* Then I used grep command to find the word in the wordlist file.
Ans : ebqattle

![image](https://github.com/it-crypto/WriteUp/assets/54020728/3b446d25-3577-4b7c-8e8f-8ddf8fd5ef0b)

After finding the password, decrypt the gpg file it gives zip file and then unzip the zip file it gives the original file.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/6ddb39b8-bf73-4780-a7c2-3edba4a42a9b)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/3bac3d3b-e6c7-45fa-91aa-7b6fb0d26101)

* Find the SSH password of the user James. What is the password?

I used grep -iR to show the contents.

Ans : vuimaxcullings

![image](https://github.com/it-crypto/WriteUp/assets/54020728/4e7078b9-909e-4e2e-9aa4-41d37a5ed0e6)

* What is the root flag?

*Here when we login as james, he had the access to root.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/5dad51a0-f8fa-415a-a949-393d48776567)


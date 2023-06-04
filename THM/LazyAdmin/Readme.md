# Lazy Admin

# Reconnaisance

* Scanning

![image](https://github.com/it-crypto/WriteUp/assets/54020728/ca006b17-c74e-4bb4-9c6b-edbed22e2af4)

* Directory Enumeration

![image](https://github.com/it-crypto/WriteUp/assets/54020728/b0f715c6-e098-4e20-ba8e-8822dddbb398)

* From the directory enumeration we found that there is a directory.
* On browsing the directory we found that a CMS 

![image](https://github.com/it-crypto/WriteUp/assets/54020728/62cd2c8a-d3f8-430e-a013-3868810633e2)

* Lets try enumerating the with the found directory and check what will be the outcome.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/58166db5-0f94-416e-afa2-6e3ee81ec34a)

* There are many interesting directories we found, lets check out.
* From one of the directories, we found some interesting files.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/86a0d0a5-01ee-47b7-917c-438a073de114)

* Gobuster

![image](https://github.com/it-crypto/WriteUp/assets/54020728/fdcccdc3-53ce-43f4-acb6-5225fdf9a50a)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/5e641731-60e3-4b72-963b-4c9f695b364d)

* From the mysql_backup we found some credentials : user and pasword which is in hash format.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/295049a1-7104-4a1e-b51b-87d9d8d27d41)

* Used hash-identifier to know what type of hash it is.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/914efdc4-f83e-4900-8b22-1d2159b81dc4)

* Using hashcat to recovery the password.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/ab189667-04fe-46bf-8b7b-b62591e64994)

* With the credentials we have found that we are able to login in.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/974810d9-43f6-40c3-ac1c-1ebd82f0eb8d)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/bdc8ef44-a645-4188-9134-4f3c8859d0d5)

# Exploit

* In the ads section of the dashboard, copied the reverse shell

![image](https://github.com/it-crypto/WriteUp/assets/54020728/214ae8e9-f2c0-4276-a2c6-596028bfcb15)

* We can see the file in the ads directory

![image](https://github.com/it-crypto/WriteUp/assets/54020728/f7a2d039-5693-46c6-b813-139f693c6857)

* Using netcat to get the shell

![image](https://github.com/it-crypto/WriteUp/assets/54020728/b21dd208-9e97-42c0-8698-0a5fd523309a)

* We tried to find out what privileges are present

![image](https://github.com/it-crypto/WriteUp/assets/54020728/108f9a23-2bce-4d1d-93c8-056e96173eeb)

* We found some files, in which we saw some 

![image](https://github.com/it-crypto/WriteUp/assets/54020728/edeb31ff-4e61-4b27-93b5-f4f10b1a97ff)

* Using netcat to get the shell

![image](https://github.com/it-crypto/WriteUp/assets/54020728/d197b3cc-7d22-480e-a191-f5cacdf9456b)

# Flag

* User.txt

![image](https://github.com/it-crypto/WriteUp/assets/54020728/32c3be1c-4383-4827-9eb6-cd53811540d5)

* Root.txt

![image](https://github.com/it-crypto/WriteUp/assets/54020728/97297fb3-5d58-4f1d-b871-dd89df4d0f21)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/6f1ab9b5-578b-4d71-95a2-b5f5dcd12e80)

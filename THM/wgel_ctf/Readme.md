# Wgel CTF

* Enumeration

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/6da382b0-40e8-40e6-a21e-7dbcecb36700)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/974c23b5-5ef3-4d65-a389-7d5dfa1b19e5)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/babf2f73-dde8-4ef4-888a-3cc6e4463a86)


* From the index.html file, we can see that there is some data missing, on inspecting it we found a name, it can be username for ssh.
  
  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/f77652cf-a50e-4d0f-abfe-b57836325c52)
  
* We found that ssh port is there but we dont have any credentials.
* From Directory Enumeration, there are some ssh files private key.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/fa6022c6-bc78-4903-a8f2-04383545f501)

* Lets see whether we can find any password from here.
* When tried to find if there is any password from the private key, it says no password.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/22a977f5-8692-4601-8e55-bd96ab46cda8)

 * Using private key with the username and no password we are able to login in to ssh.

    ![image](https://github.com/it-crypto/WriteUp/assets/54020728/0bb96f25-da4a-449d-ab4e-8bfb7bd71532)
* Found the user flag with find command
* Commands used:
   1. find . -type f -name "*flag*" -- it will result in all the files where the flag name is present in the file.
  
   2. find . -type f -name "*flag*" -exec cat {} +
  // We can find from here what will each word does:

  https://explainshell.com/explain?cmd=find+.+-type+f+-name+%22*flag*%22++-exec+cat+%7B%7D+%2B
  
  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/9ce73f3a-6a3b-41f8-bb54-145a3b2c23f9)

 # Privilege Escalation
 * Using sudo -l we got some entries. Lets check

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/2e3e82cf-dba3-4f74-a2d8-4c5dc115c5ad)
  
 * References:
   1. https://www.hackingarticles.in/linux-for-pentester-wget-privilege-escalation/
   
   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/d10d5d96-78a8-4b4a-81d0-c340cef07edd)

   2. https://gtfobins.github.io/gtfobins/wget/#sudo
   
   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/b4628e64-d340-41cf-9265-d5562e58d218)

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/7b3cc3d2-f8c7-4f44-9c12-0bee7f5e5b4c)

 * Root flag

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/6c86f4d0-6ae3-40a0-add8-18e11b3edcbd)
  


  



   




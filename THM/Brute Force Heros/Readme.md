# Brute Force Heroes

* Brute forcing using differnt tools
   1. Hydra
   2. Patator
   3. Burpsuite
   4. ZAP Proxy

## Brute forcing against DVWA application

#### BurpSuite

* We are provided with the username and for the password to crack they have provided a wordlist which will be helpful in brute-forcing.
  
   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/6e1697d9-e4c9-46f4-872b-5feb184f4b23)
  
* Tried to login with different usernames and passwords and checking what are the requests/responses got

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/4d208932-ee40-45bc-9de1-c7eb5bc58b7f)

* We can use intruder tool in the burpsuite to enumerate further

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/f82fdf60-f3ea-4bf1-ab8e-6014a866ba5b)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/652356e3-fd85-4d19-bc94-ffaa1a45c079)

* But this is the right tool as mentioned we need to know more details which cannot be provided by the Intruder.

#### Patator

* We can install patator using command sudo apt install patator

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/52f2a372-cf3b-4dd0-a020-67a77f53fa6b)

* We can use the module http_fuzz for this let us know how to use it

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/212ce5d2-3cc4-4ab2-a14a-0e8fbba43b58)

* This is the format we need to use for constructing the command

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/a35ae02f-a79e-4a53-a484-4ca4e08daa01)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/7a32738f-dff9-49cb-b640-c02680a737d8)


  


  
  


  

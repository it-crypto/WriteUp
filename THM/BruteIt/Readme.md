# Brute It

# Reconnaisance

* Perfomed a nmap scan to get all the details.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/09fe2418-9c00-4094-828b-810e8ec795cb)

 * Directory Enumeration

 ![image](https://github.com/it-crypto/WriteUp/assets/54020728/23fc2cad-b14b-499e-931a-315b1bb7d69f)

* Found an admin panel, trying to check for the credentials.
  
![image](https://github.com/it-crypto/WriteUp/assets/54020728/472b345a-ce5d-43b7-b771-0419d44b50e2)

* Used hydra to brute force the password.
* Reference: https://infinitelogins.com/2020/02/22/how-to-brute-force-websites-using-hydra/
* Command used: sudo hydra -l admin -P /usr/share/wordlists/rockyou.txt <IP> http-post-form "/admin/:user=admin&pass=^password^:Username or password invalid"

![image](https://github.com/it-crypto/WriteUp/assets/54020728/3542f831-9dd7-4888-b653-2d902fe8fb1a)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/92ae9370-5e73-4da8-848a-a1fddada84a5)

* From the website, got a RSA private key, using john got the paraphrase.
* Command used: john id_rsa.hash --wordlist=/usr/share/wordlists/rockyou.txt

![image](https://github.com/it-crypto/WriteUp/assets/54020728/1671ad9d-ebe9-4f51-830f-cca7990e64c3)

* With the passphrase we got and using ssh with username as john we are able to get the shell.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/f980e39f-830f-48da-8216-abc94547ee70)

# Privilege Escalation

* Reference:
  https://www.hackingarticles.in/linux-for-pentester-cat-privilege-escalation/

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/c78ac8f4-b8aa-4f47-9cf1-c5a2415ebf4e)

* Using hash identifier to know what type of hash it is.
   
   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/45d57c43-d6af-4555-9374-e1b12e6305be)

* Using john the ripper with the hash copied, cracked the password.

     ![image](https://github.com/it-crypto/WriteUp/assets/54020728/cfb0953e-4e1a-4850-84be-ad131da16873)

* Using the password we got, switching the user to root we are able to login as root and get the fag.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/11f4a097-44df-4c03-9ab7-7d32752cecaa)


 

 



  








 

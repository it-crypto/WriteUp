# Intermediate Nmap

#### Scanning

* Used Nmap to scan for ports running on the machine.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/d9b7edf0-6898-471c-82e6-8807b75c561e)

* After scanning, there are three ports open 22, 2222,31337. In the port 31337 there are some credentials.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/27d251ad-d00f-4aa9-b0eb-9dde787966db)

 * One of the used commonly used ports(22) ssh service is open. Using the credentials we got from the port 31337, logged in to ssh.

    ![image](https://github.com/it-crypto/WriteUp/assets/54020728/8a5b9da2-d990-45c2-aa5f-ed57be0990a1)

* After checking the contents of the directory, found the flag.
  
  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/79e3acab-0a34-48b6-a3de-524d56dcc98d)




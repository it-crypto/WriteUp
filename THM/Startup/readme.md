# Startup

* In this room, we try to Abuse traditional vulnerabilities via untraditional means.

# Enumeration

![image](https://github.com/it-crypto/WriteUp/assets/54020728/21755728-c0ad-4f00-9586-6197bf16088c)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/f03dbce5-b009-4912-996f-73e3ae58633d)

# FTP/HTTP Enumeration

* In this we are trying to use whether we can upload any files in the ftp directory from ftp 
* I hav created a sample text file and uploaded to the ftp directory

![image](https://github.com/it-crypto/WriteUp/assets/54020728/db7a3008-23a7-4a4f-85cf-efbbbe1d9a2e)

* I have checked in the url and we can see that the file is uploaded to the directory.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/2920a9d2-8c5c-44b1-a811-c6d5c81ecd57)

* Trying to upload the reverse shell in the ftp directory.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/63828a46-8e93-4575-bd16-a3d1617eac0d)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/8e9cc417-4014-4aa5-9c3a-1b9f948ece57)

* After uploading the php file and listening to the port we got the shell.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/cd93a700-a21f-41d4-a588-6f22a82d2241)

* using python to get bash shell

![image](https://github.com/it-crypto/WriteUp/assets/54020728/4fea30e8-e1d9-44c2-94fd-a5cbd3d65e70)

* After getting the shell, tried to find the recipe 

![image](https://github.com/it-crypto/WriteUp/assets/54020728/9034d345-bf4e-4640-8b52-1fdd8b3ef72c)

* Trying for other directories to see for something which doesnt belong to

![image](https://github.com/it-crypto/WriteUp/assets/54020728/4c0b9456-8827-47fe-b589-2b746fc984bc)

* From one of the directory we found there is a pcap file, so copy the file to ftp directory.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/b49f8dac-98e7-437d-8e84-7f13d9096617)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/56f7e1b1-6044-43bd-ae68-80d40ff1dc03)

* From the found pcap file, I have filtered data and checked the file, there is a session which is having the data and from there we can find the data.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/0ab5d358-87f1-4b24-916d-edb88f0739ba)

* Using the data we found we can try to login in another user and get the user.txt file

![image](https://github.com/it-crypto/WriteUp/assets/54020728/c53d2807-fa17-4e1f-9509-0cc106977c3b)

* We found that there is a sh file which then uses /etc/print.sh file and performs a cron job

![image](https://github.com/it-crypto/WriteUp/assets/54020728/1d1d7be7-89e0-4551-9e0f-8a236cde19fb)

* So, wrote a script that triggers the cron job that can execute after some time and get the access to the root when listening to the port.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/8f68fc34-8b53-423d-aee9-420ca0f0d175)

* We have set that port to listen using nc after a minute, the shell file gets executed and we have root access and we get the root.txt file.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/3e37a028-45e1-4f44-8dd4-65489b375507)










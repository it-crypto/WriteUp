Bandit for learning the linux commands and understanding them.

In this each level gives the password to the next level.


FIRST Level (0)
1. First login in to bandit0 using ssh and password "bandit0"  using the port 2220
command : ssh bandit0@bandit.labs.overthewire.org -p 2220

2.In the readme file the flag for next level is stored.
Ans : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

![image](https://github.com/it-crypto/WriteUp/assets/54020728/d3ce678f-adeb-448d-be23-c7198c746704)

SECOND Level (1)

Login into ssh using the bandit(Levelno) and password obtained from the previous level.

1. The file is stored in “-” dashed file. To read the contents of the dashed filename we can use
command : cat ←

flag : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

![image](https://github.com/it-crypto/WriteUp/assets/54020728/ffb50df1-fb09-4484-886a-6c6f9e5f179b)

We can use other command also. Command: cat ./-

![image](https://github.com/it-crypto/WriteUp/assets/54020728/3f7f5775-6b81-4306-a46b-0b929a830e24)

THIRD Level(2)

1. File is stored in spaces folder. So we can use entire file as string enclosed in quotes.
   
flag: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

![image](https://github.com/it-crypto/WriteUp/assets/54020728/391e16a1-96a9-4ae2-85b8-c1ef60353236)

FOURTH LEVEL (3)

1. The file is stored in the directory

flag: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

![image](https://github.com/it-crypto/WriteUp/assets/54020728/d0b38c46-ed2e-4fe5-bbd2-3e8ba32774ea)

FIFTH Level (4)

1. The file is stored in directory and the file is of human readable format
   (I tried opening every file, but in case the files are less so it is easy to search but if there are so many files, this process take so much time. Need to look for alternative . I need to search on find and ls commands).

Flag : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

![image](https://github.com/it-crypto/WriteUp/assets/54020728/90c05e86-becd-4eae-a900-35451cb4d67f)

SIXTH Level (5)

1. Find the size which is human readable, 1033bytes in size and not executable.
Command : find -size 1033c
here ‘c’ refers bytes
flag : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

![image](https://github.com/it-crypto/WriteUp/assets/54020728/cac1d1f9-5348-447f-aaa3-a427bbc21e75)

SEVENTH Level (6)

1. Find the file which is  owned by user bandit7, owned by group bandit6 and 33bytes in size.

Command:  find / -user bandit7 -group bandit6 -size 33c

flag: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

![image](https://github.com/it-crypto/WriteUp/assets/54020728/7aec7a95-a4a3-448e-8cea-8ac035a06ddd)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/769983ba-c3ef-4927-8b18-566fc9be9dc9)

EIGTH Level(7)

1. Find the password which is stored in the data.txt near to the word millionth.
 (When I printed the contents of the line, there are so many lines, and in the question they mentioned grep so used grep command for filtering.)

Command : grep -i “millionth” data.txt 
(Here -i used for ignoring case sensitive)

flag : TESKZC0XvTetK0S9xNwm25STk5iWrBvP

![image](https://github.com/it-crypto/WriteUp/assets/54020728/a535d6b9-1088-47ce-a4dd-aa350867c13f)

NINTH Level(8)

1. Find the password stored in the data.txt file in which only one line of text that occurs only once.
(//As the only occurrence, it is unique, I tried to use grep but grep is not used for uniqueness, I tried with the “uniq”, but before we use uniq, we need to sort the data first  )

Command : cat data.txt | sort | uniq -u
flag : EN632PlfYiZbn3PhVK3XOGSlNInNE00t

![image](https://github.com/it-crypto/WriteUp/assets/54020728/86b7e168-c0a8-47c5-8c04-f2b4705d6b93)

TENTH  Level(9)

1. The password stored in the data.txt in one of the human readable strings preceded by several “=” characters.
(I used the word strings to check what type of data is printed. I found some of the passwords preceded  by = characters)

Command : strings data.txt | grep ====
flag : G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

![image](https://github.com/it-crypto/WriteUp/assets/54020728/d672de33-253b-4176-b780-7a95831f4819)

ELEVENTH Level (10)

1. The password stored in the data.txt contains base64 encoded data.
(I used base64 – decode option on data.txt)

Command : base64  --decode data.txt
(or)
command : cat data.txt | base64 --decode

flag : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

![image](https://github.com/it-crypto/WriteUp/assets/54020728/3abfa2f7-fc21-4e62-9da9-eab92152d0c7)

TWELVE Level (11)

1. The password stored in the data.txt should be rotated 13 times for both upper case and lower case.
(// Can use rot-13 online tool)

(tr command is used to translate/delete characters.  In this scenario tr takes two arguments first argument is set of charaters(lower/upper) and second argument is to which letter it have to be rotated to. For example,here they mentioned that 13  times rotation. So  a/A is to be replaced by n/N like that)

(// here first translating the lower case and then upper case)

Command  : cat data.txt | tr ‘[a-z]’ ‘[n-za-m]’ | tr ‘[A-Z]’ ‘[N-ZA-M]’
flag : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

![image](https://github.com/it-crypto/WriteUp/assets/54020728/eb683f5d-1b1a-432c-a921-03a3146bba88)

THIRTEEN Level (12)

1. The password is stored in the data.txt which have compressed hexdump data.
(// Here we have to use many commands as the data is being compressed many times so make sure to see what type of file it is and based on that rename the file and decompress,… follow the same procedure until the file is ascii text)

Steps: 1. First created a directory decompressdata (directory name can be anything)
Command : mkdir tmp/decompressdata
Step 2: Copy the data.txt file into the folder.
Command  : cp data.txt  tmp/decompressdata
Step 3 : I made a copy of the data.txt file so that it can be used (for backuppurpose)
Command : cp data.txt  data1.txt
Step 4: I have used the hexadecimal command with option r to reverse the data and read the data into the new file.
Command : xxd -r data1.txt > data2.txt
Step 5: Based on the type of data I renamed the data (bz2,gz,tar) and decompressed the data using the appropriate commands
Commands: bzip2 -d filename.bz2
                    gzip -d filename.gz
                    tar xvf filename.tar


Flag: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

![image](https://github.com/it-crypto/WriteUp/assets/54020728/0d7104e3-6fe7-4a16-9ac6-9817fb8b218d)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/db10140d-e2d2-4585-b320-becca270e826)

Fourteen Level (13)

1. The password is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level.

(For this we need to get into the bandit14 for that they said that we can use sshkey present in the bandit13 with that we need to get into bandit14)

Command: ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

flag : fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

![image](https://github.com/it-crypto/WriteUp/assets/54020728/2c0aa576-4518-49ba-b06b-a8bde58fe4d6)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/0588cf32-419e-42f4-b307-da666db602d7)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/f345d548-ab4a-4f3f-9235-4bae7372ebba)

FIFTEEN Level (14)

1. The password can be retrieved by the connecting to the localhost on port 30000
(telnet can be used to connect to other systems but it is not secure, here when connecting, we provided the password we got from the previous level.)

Command : telnet localhost 30000
flag : jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

![image](https://github.com/it-crypto/WriteUp/assets/54020728/ce99c885-97d2-44a9-a5b3-e3d63ad8537f)

SIXTEEN Level (15)

1. The password can be retrieved by connecting the localhost on port 30001 using SSL encryption
(SSL – is to identify whether we are sending request to the correct website and the web server should provide a certificate to prove its authenticity)

To connect to a server, you need to supply a hostname and a port. 

using the openssl s_client -connect <hostname>:<port> syntax, 

 Command:openssl s_client -connect localhost:30001.

Here, s_client implements a generic SSL/TLS client which can establish a transparent connection to a remote server speaking SSL/TLS.
Also,-connect <hostname>:<port> specifies the hostname and optional port to connect to.

Flag : JQttfApK4SeyHwDlI9SXGR50qclOAil1

![image](https://github.com/it-crypto/WriteUp/assets/54020728/a1ead6f2-4ddf-42b0-869a-257675ad66ae)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/70e2eecb-a18a-4c7d-9913-31fbe52265a9)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/116051a9-5d1c-452b-b5e4-ebf41c9d315a)
	
SEVENTEEN Level (16)

1. The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t.

(First we need to port scan to find out  what ports are open, we need to do openssl on open ports to find  that which is the correct one. I found the port 31790 to be correct one. It have the private key. We need to copy the private key. For that we need to create the directory under tmp folder and store the key in the file and then use sshkey to connect to next level. But it shows the permissions are set to public it is bad. We need to set the permissions only for the user to read. Then you can connect to next level and see the etc / bandit_pass/ bandit17 )


Command : nmap  localhost -p31000 -32000
                    openssl s_client -connect localhost:portno
                    mkdir directory_name
                    cd /directory_name
                    nano filename
                    ssh -i /filepath bandit@localhost
                    chmod 400 filename
                    cat etc/bandit_pass/ bandit17

flag : VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

![image](https://github.com/it-crypto/WriteUp/assets/54020728/04700600-c2db-42e4-a7e0-09f070755bf1)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/fb5972b4-42f5-4ba7-b5c9-d68b9990896b)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/c14bf4f7-a425-4565-a774-3a4ac3d57b9e)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/f3405d70-5c0e-484e-a137-50146949a038)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/a6bca8e8-62e2-4812-ae28-6f907e7a4be2)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/cf721044-11df-478d-a344-5256a9db950b)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/8f55ab06-e5ac-475f-9952-03e52e8f3be1)


EIGHTEEN Level (17)

1. The password is stored in passwords.new. But there is only one line difference between passwords.old and passwords.new

(I used diff command and then used grep to find the password is in passwords.new)

Command : diff passwords.new passwords.old
                    grep ‘string’ passwords.new

flag: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

![image](https://github.com/it-crypto/WriteUp/assets/54020728/1ba6c66d-ba4a-4b41-ab45-168966b93468)

NINETEEN Level (18)

1. The password is stored in the readme, but as soon as login we logout.As the change has been done in .bashrc file to logout as soon as logged in.

(// I tried to do ssh from previous level using ssh but it didn;t work. Instead, we can append commands along with ssh they give the result)

Command : ssh bandit18@bandit.labs.overthewire.org -p 2220 ls -al
                    ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme

flag: awhqfNnAbc1naukrpqDYcF95h7HoMTrC

![image](https://github.com/it-crypto/WriteUp/assets/54020728/f37c9aad-88ae-4407-a1a3-457b52e63e74)

TWENTY Level (19)

1. Set the uid for the file present in the directory and read the password.
(//UID : set the user id. When we set the id it will run as the root instead of that user. It will escalate the priveliges)

Command : ./bandit20-do cat etc/ bandit_pass/bandit20

flag : VxCazJaVykI6W36BkBU0mJTCM8rR95XT
	
![image](https://github.com/it-crypto/WriteUp/assets/54020728/b3e862e4-70d0-4931-9752-f682fac9de98)

TWENTYONE Level (20)

1.There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21). 

// The challenge is that there is a setuid binary when executing, it stated that it requires a port to connect and if we sent the current level password it will give then the next level password. For that we need to use nc for transfer of requests from one port to another port. For that we need to check what ports are open on our local host. We cannot use that ports. For that purpose we can do nmap.


Command: nmap -sV -sC – p – localhost (// I just tried this nmap command to check the services)
( When I did nmap. I found some ports : 22, 3000, 3001…..)

// I used tmux for splitting the screens 

Command : tmux (Ctrl + B  % - for vertical split)

Command : nc -lp 6000 (l : listening and p : port)

Command : ./suconnect 60000

// From nc listening side , I just typed the current level password and in return I got the next level password.

flag: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

![image](https://github.com/it-crypto/WriteUp/assets/54020728/bd8886e4-e961-44c8-8d74-1a61889d09e2)

TWENTYTWO Level (21)
1. A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

// cronjobs are programs running automatically at regular intervals. 
In Linux, there are multiple folders that can contain these cronjobs: cron.d, cron.daily, cron.hourly, cron.monthly, crontab, cron.weekly. The folders contain files with instructions on how the programs are run. 
It starts with the first five columns, which indicate at what time/interval the program should be done. Next is the command/program that is to be executed. 

MIN HOUR DOM MON DOW CMD
Crontab Fields and Allowed Ranges (Linux Crontab Syntax)

Field    Description    Allowed Value
MIN      Minute field    0 to 59
HOUR     Hour field      0 to 23
DOM      Day of Month    1-31
MON      Month field     1-12
DOW      Day Of Week     0-6
CMD      Command         Any command to be executed.

Here in the task, they have mentioned that we need to check for etc/cron.d  directory in that I have found so many files but for this level, I have checked the cronjob_bandit22 file. In that some data is there. 
For one file they have gave read permission to all and other permissions only to owner and they have copied the contents of the next level password to the file present in the tmp directory.

When listing the contents of the file we can see the password for next level.

Ans : WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff

![image](https://github.com/it-crypto/WriteUp/assets/54020728/a17b09b1-9fe0-4aa8-995a-28d93612a309)

TWENTYTHREE Level (22)

1. Cron jobs

There is a shell script which will give the password of the user who executes it i.e., it will take who is the current user and then executes and give that user password. But in the scenario, I require the another user password. I cannot execute the another user so I copied the code and created a directory in tmp folder and modified the existing code and I got the flag.

Original code:

![image](https://github.com/it-crypto/WriteUp/assets/54020728/3b2506fd-94b9-415c-a7e8-9a4732b0afef)

Modified one:

![image](https://github.com/it-crypto/WriteUp/assets/54020728/0222c246-18f1-45d6-a333-c6bfd1dff381)

Here I changed the first word and I gave $1 i.e., like command line argument it takes the word given when executing the script.

Command  : ./job.sh bandit23

Ans : QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
	
![image](https://github.com/it-crypto/WriteUp/assets/54020728/2bc9fb90-869b-4284-9f2b-1cdc0aaa8188)	

TWENTY FOUR (Level 23)

Q.  A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
	
// In this level, a cron job(shell script)  will be executing so we need to create a script file and copy the script file(created by user) to the directory mentioned in shell script(cron job) and then the file will be executed and the we will get the password.

Ans: VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
	
![image](https://github.com/it-crypto/WriteUp/assets/54020728/62a4aa48-e810-413a-bf54-71b7f57aa073)

TWENTY FIVE (level 24)

Q. A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode

// In this level, we need to give the password of the above level and 4 pin code( 1000) combinations. I tried giving the any pin and tried. Its better to write a script to execute

// Usually the combinations are 0000 – 9999. When I tried to do all the combinations it is taking time and the connection is getting timed out. So I created a new script from 5000 – 10000.  I got the flag.
First I listed all the combinations with password and pin and then I gave the combinations to  the nc and then printed them in the file.

Command :  cat code.txt | nc localhost 30002 > results.txt

Ans: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d
	
![image](https://github.com/it-crypto/WriteUp/assets/54020728/0bf05764-6c42-4501-ad26-dbe5cb0e2bb6)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/ee2df0da-cbe6-4cf6-ac6e-7b5ab04ed43c)

TWENTY-SIX (level 25)

Q. Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.

// In this we need to find the use of more (options) and different uses of other uses and try to get the flag.

Ans: c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1

// In this level when we list the contents, we can see that there is a private key when we try to login in to that the connection timed out. So we checked if there are any other folders/files related to the bandit26 and there we found a file “showtext”. The contents of the showtext tells us that the more command is used in shell and the text in ’text.txt’ is very short, meaning the whole text can immediately be displayed. more does not need to go into command/interactive mode. If we make the terminal window smaller, more will go into command mode. We can then use v to go into vim. Now we can rescale the window.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/033b2c5e-0687-4580-ba6a-d4f80503a04b)
	
// so before login in to the bandit26 zoom the screen(ctrl+) and then login, then more(50%) will be displayed and then press “v” to enter to vim mode and then press “:e path” to show the contents of the password file (:e cat /etc / bandit_pass / bandit26)

![image](https://github.com/it-crypto/WriteUp/assets/54020728/80a5f3f6-8408-4432-a6dd-e9056e30abbd)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/c9d657ee-bc07-46ac-8624-6257e678be75)

// After pressing v then it will enter 
	
![image](https://github.com/it-crypto/WriteUp/assets/54020728/ad5d77b9-838a-4922-a84a-6aa8a4f95ad2)
	
and then press

![image](https://github.com/it-crypto/WriteUp/assets/54020728/f4c68fa5-5d5b-4971-9488-b119a0f935c3)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/e83372f0-36a8-472c-b6e4-657589de7e59)

TWENTY-SEVEN (level 26)

Q. Good job getting a shell, find the password for the next shell

Ans: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

// As the bandit26 is used for this, we know that we need to zoom the screen so that more command will be shown and then we can work. For this we need to enter the shell so for that we that we can use
“:shell” command in vim mode. But it uses default shell so we need to use commands
“:set shell=/bin/bash” and then enter the shell using “:shell” command. 

![image](https://github.com/it-crypto/WriteUp/assets/54020728/8d1a5682-4785-4d25-9349-9ebec3df67cb)

First we enter :shell but nothing happens so we have to set the shell.
![image](https://github.com/it-crypto/WriteUp/assets/54020728/6bcc0d31-072e-4fc1-90fe-617da1c557cb)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/7de40414-be2f-46b8-ac65-96814acce19c)

//After setting the shell and then using the command “:shell” we are able to enter the shell.
![image](https://github.com/it-crypto/WriteUp/assets/54020728/0c11beac-3ed3-4072-a661-d274c5d2fc67)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/80748123-7eba-4e78-9833-4064f2b81664)

TWENTY-EIGHT (level 27)

Q. There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo. The password for the user bandit27-git is the same as for the user bandit27.

// For this we need to clone the git repo. First I tried to git clone directly from current directory, I got the error so I created a directory in tmp (mkdir tmp / gitcl ) and tried git clone there  but I faced the error like this, this means that I am trying to connect to port 22(default ssh port) but here we are using port 2220 so modified the port and it worked.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/f30da32d-44ef-4317-9e13-ea7e01081075)

Ans: AVanL161y9rsbcJIsFHuw35rjaOM19nR
	
![image](https://github.com/it-crypto/WriteUp/assets/54020728/43f36a2a-a5c5-40c8-a4a3-bab76dd3b38c)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/3e9864c3-7db8-445b-b85c-50bcf1b6f60f)

TWENTY-NINE(level 28)

Q.  There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo. The password for the user bandit28-git is the same as for the user bandit28.

// In this when I cloned the repo, I found the readme file but in that the password contents are masked so I tried to search around the files and I tried to grep for “bandit29” but I didn’t get any output. When I searching I found  a hash and when I checked the hash it belongs to master and the password is shown.

Ans: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

![image](https://github.com/it-crypto/WriteUp/assets/54020728/c7045e50-1b29-4032-8046-7e000d192d5a)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/0633f6ca-bd8d-4217-841a-00a8d2bd421c)
                                    (or)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/f3c86a3c-43dd-4446-a370-e7002c68e0da)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/4d148de4-5c30-4ce8-89ef-8fe97ff0974f)

THIRTY (Level 29)

Q. There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo. The password for the user bandit29-git is the same as for the user bandit29.

// In this I cloned a repo and tried to find the password but nothing is found. I checked the readme file it states that no passwords in production. I have checked if there are any branches and I found some branches and tried checkout to that branch and found file.

Commands  :  git branch -a
                        git checkout branchname

Ans : xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

![image](https://github.com/it-crypto/WriteUp/assets/54020728/c97b244a-5fe4-4c6e-9449-a734b375cb09)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/1963ca91-8a0e-4952-bff3-fa4696b9f647)
	
THIRTY-ONE (level 30)

Q . There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo. The password for the user bandit30-git is the same as for the user bandit30.

// git tag : different points in the revision ( https://www.toolsqa.com/git/git-tags/, https://www.freecodecamp.org/news/git-tag-explained-how-to-add-remove/)

Commands :  git tag
                       git show “filenamefromtag”

Ans : OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt

![image](https://github.com/it-crypto/WriteUp/assets/54020728/0a85f4f5-8339-443f-bf6b-c648ec3eeef9)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/46eb26bb-59bd-4d6b-ba3c-e0b720c600c1)
	
THIRTY-TWO (level 31)

Q. There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo. The password for the user bandit30-git is the same as for the user bandit31.

// In this level, the task is to create a file and add the file (should check whether that file is ignored or not because (when viewed the contents of the .gitignore file.

Command :  cat .gitignore  Output: *.txt ) so here *.txt files are ignored.
So removed the .gitignore file and then added the file and committed and pushed to the origin.

Ans:  rmCBvG56y58BXzv98yZGdO7ATVL5dW8y

![image](https://github.com/it-crypto/WriteUp/assets/54020728/c314ae52-fe7c-4d6b-888f-5f9286f36427)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/314d9c75-0cc2-49d8-a22c-9bed537036a8)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/a83d7823-5b7b-4ec9-aef8-b9836b625797)

THIRTY-THREE (level 32)

Q. After all this git stuff its time for another escape. Good luck!

// In this we will be entering the executable called uppershell so we have to come out of the shell so we will be using $0 and read the contents of the password.

Ans : odHo63fHiFqcWWJG9rLiLDtPm45KzUKy

![image](https://github.com/it-crypto/WriteUp/assets/54020728/8b337de7-0b20-4555-bb66-b456573bc138)




 Level 0

ssh: ssh leviathan0@leviathan.labs.overthewire.org -p 2223
password : leviathan0

Level 1:

Q. Find the flag.

// when listing the contents, found a backup directory and in that there is a html file, so used grep to find the password for the level

Ans : PPIfmI1qsA

![image](https://github.com/it-crypto/WriteUp/assets/54020728/018875a4-aa03-412b-b196-b0e785a0de31)

Level 2:

Q. Find the flag

// In this level, there is a executable called check which takes the password as input. I tried different passwords and tried but no use. 

I used a command called “ltrace” to list the system calls  and then I found that after password is being inputted it is comparing the string and giving the shell access to leviathan2

ltrace is a program that simply runs the specified command until it exits.  It intercepts and records the dynamic library call which are called by the executed process and the signals which are received by that process.  It can also intercept and print the system calls executed by the program.

ltrace shows parameters of invoked functions and system calls. To determine what arguments each function has, it needs external declaration of function prototypes.  

Ans: mEh5PNl10e

![image](https://github.com/it-crypto/WriteUp/assets/54020728/cb92f580-1e32-4239-886e-3366a805de42)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/1ff45b68-de27-4771-8e81-bdb5c03e68c3)

Leviathan3

Q. Find the flag

// in this level,  I found a executable, on executing it requires filename, so I checked for the password file it says no access.
I found there is access call and there is bin/ cat to print the contents of the file. I have checked, but if there is space between the filename it considers as two different files. So lets create a symbolic link between password of level3 and tmp folder file and try to access.

Ans : Q0G8j4sakn

![image](https://github.com/it-crypto/WriteUp/assets/54020728/72f5775f-bf27-4e6e-909e-0886e9729c20)

leviathan4

Q. Find the flag

Ans : AgvropI4OA
// in this also, they are comparing the string with “snlprintf” and after we will get access to shell.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/cc7b15da-2230-4d47-a029-b438737e2c9f)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/7de59833-ba69-421b-9bf0-b8cf4303e928)

leviathan5

Q. Find the flag

Ans: EKKlTF1Xqs

// I found the binary value : 01000101 01001011 01001011 01101100 01010100 01000110 00110001 01011000 01110001 01110011 00001010

After decoding from binary to text I found the flag.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/c83a68a5-4897-4e9d-9f65-d049b65604f3)

Leviathan6

Q. Find the flag.

Ans: YZ55XPVk2l

// In this level, an executable is there it wants to link the file which is not there, so we create the file and link to the etc/leviathan_pass / leviathan6 so that it can read the data.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/2dbbae16-525f-46db-b42d-b1327f7fe676)

Leviathan7

Q. Find the flag.

Ans : 8GpZ5f8Hze

// in this level, there is a executable which is asking for four digit pin, so brute force it and there after some time we find the shell and from there we can get the password.

![image](https://github.com/it-crypto/WriteUp/assets/54020728/a97692c2-0f59-4877-bff6-dd4f3b697a2c)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/04679bd1-fbd9-4cb6-9f3d-51d6356e8443)
![image](https://github.com/it-crypto/WriteUp/assets/54020728/42c2bbcb-8051-4dea-8974-f09b19bff7de)

Leviathan8

![image](https://github.com/it-crypto/WriteUp/assets/54020728/e4f04c8b-8c0e-4527-afab-422b4e4d0526)


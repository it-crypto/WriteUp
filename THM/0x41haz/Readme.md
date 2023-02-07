## 0x41haz
- In this challenge, we are given an executable file, in which the file is of unknown type.

- I have used the file command to know what type of file it is. It is ELF 64-bit MSB but it states it is not an executable.

- Somewhere the file format had changed, from the definition, we need to change some bits of the file so that we can know the original file.

- In order to alternate the header you can use any hexadecimal editor like hexcurse.

- The 5th byte defines format 32 bits (1) or 64 bits (2)

- The 6th byte defines endianness LSB (1)  MSB (1)

![image](https://user-images.githubusercontent.com/54020728/215550640-d5962b1f-60d7-4abe-bf4b-1072eeba46ff.png)

- I have used the hex editor to change the value of 6th bit to 1.

![image](https://user-images.githubusercontent.com/54020728/215550768-e46c095c-27d4-428a-8703-788ad2080c13.png)

![image](https://user-images.githubusercontent.com/54020728/215550811-f150c925-c62e-4cb4-8200-f39405bd3434.png)

- The 6th bit is showing 2, lets change to 1 and see what type of file it is.

![image](https://user-images.githubusercontent.com/54020728/215550924-24804057-5260-4876-8d65-199212820520.png)

- After changing the 6th bit to 1, and executing file command on the executable we can see that is the stripped 64-bit MSB executable file.

![image](https://user-images.githubusercontent.com/54020728/215551125-659aa29c-c3c4-418d-8e8c-9ff5f4347589.png)

- I have performed strings operation to check if I can find any hint or flag, but I didn’t find anything.

![image](https://user-images.githubusercontent.com/54020728/215551371-2659ba69-0302-48d3-8eb5-5a11c3fd256a.png)

- I have used Ghidra tool to see if I can find anything related to what input is being compared to.

- I have analysed and from entry function we can see that it is calling some other function.

![image](https://user-images.githubusercontent.com/54020728/215551674-d6f156e0-bb5e-4e7d-867b-4fd4354240e8.png)

- From that function, I found some parameters are being passed and they are performing some operation with the parameters.

- As it is little-endian, the MSB(Most significant bit) is placed last and the LSB is placed first so we need to reverse the values and give it as input.

- Here there are three variables, I appended the three and gave it as input to the executable.

![image](https://user-images.githubusercontent.com/54020728/215551836-ac63800a-56aa-4fe2-b88a-a52afffd11ad.png)

![image](https://user-images.githubusercontent.com/54020728/215551873-110b8414-9d8b-4141-bd5f-52981a82c30a.png)

![image](https://user-images.githubusercontent.com/54020728/215551890-0d3715f0-319e-4b88-a831-47eae9eb516d.png)

Vola!  Its correct.

Ans: 2@@25$gfsT&@L

![image](https://user-images.githubusercontent.com/54020728/215551962-6aca7206-5887-4fd4-8f54-5b7c947af39f.png)


THM Room Epoch:

--> Epoch Time Converter : converts UTC time format to date format

--> Start the machine and navigate to the following URL using the AttackBox: http://MACHINE_IP 

--> From the website we can see that there is a time converter, but we need to check whether it can execute any commands.

![image](https://user-images.githubusercontent.com/54020728/215844673-2205e844-bb5d-45f6-a965-29dbb2331d5f.png)

--> I have tried few sample commands like ls, whoami but its not working.

--> From the url we can see whatever the argumnets which are passed in the input field are shown.

![image](https://user-images.githubusercontent.com/54020728/215845181-b7368eac-472e-45d6-b957-77ae79055b87.png)

![image](https://user-images.githubusercontent.com/54020728/215845352-9de4141c-522f-477a-bcd6-6f4640111d79.png)

--> I have tried giving semicolon and then executed the command.

--> Here we used ";" first to terminate the first command. Any command executed after will be executed and gives the value.

![image](https://user-images.githubusercontent.com/54020728/215845714-b437287e-a07a-401b-a494-772350570c85.png)

--> I have tried few commands but I didn't get the flag.

--> From the hint, I learnt that we need to check in the environment variables.

![image](https://user-images.githubusercontent.com/54020728/215845838-20dc8e3c-cbf8-40fd-ac79-d63148143a7a.png)

--> I have tried ";printenv" which will print environment variables and it contains flag.

Information : The printenv command displays the values of environment variables. If the name argument is specified, only the value associated with name is printed. 
If it is not specified, printenv displays the current environment variables, one name=value pair per line.

![image](https://user-images.githubusercontent.com/54020728/215846004-e8437895-154a-4cbd-a7ca-60863ac0e3fb.png)













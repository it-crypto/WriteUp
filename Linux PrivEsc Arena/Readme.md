# Linux PrivEsc Arena

* I have scanned the ipaddress

![image](https://user-images.githubusercontent.com/54020728/233780755-9f64c470-3b03-40b3-b0ea-9a3e872c77bb.png)

* When I am trying to login into ssh using the credentials, I faced the error "Unable to negotiate with IP address port 22: no matching host key type found. Their offer: ssh-rsa,ssh-dss"
* So I added the option -oHostKeyAlgorithms=+ssh-dss
* Command I used to login: ssh -oHostKeyAlgorithms=+ssh-dss TCM@Ipaddr
 
 ![image](https://user-images.githubusercontent.com/54020728/233780764-11e2808a-26ac-4308-af47-306492ca15b5.png)

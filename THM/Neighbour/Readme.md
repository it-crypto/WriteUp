## Neighbour

- In this room we will learn about the IDOR (Insecure Direct Object Reference) vulnerability.
- In this the application/website directly exposes the object which refers to any user or data or any other 
information without even authorization.
- In this any user can read/write any other users data and can make use of it and gain the access to the sensitive information
- This happens because the parameter which is used to identify the users is not secure and it is read directly 
- In order to avoid us, user should be restricted to their own account and access to other users should be forbidden.
- The parameters should be unique and difficult to crack
- After starting the machine, navigate to the following URL using the AttackBox: http://IP
- A login screen is provided, they have mentioned, we can use the guest account and there is a link.

![image](https://user-images.githubusercontent.com/54020728/217136487-d75d6bcd-06d5-43af-a952-eb3f90b9b297.png)

- When clikcing the link, we are redirected to the source code where we can find the credentials.

![image](https://user-images.githubusercontent.com/54020728/217136551-31afd2c9-e7f1-46b5-b959-45d99b943197.png)

- The credentials of the guest account are guest:guest, after entering the credentials we are able to login in the screen.


![image](https://user-images.githubusercontent.com/54020728/217136362-17ebf7e4-8c1c-42d9-bdec-55a4d89f652c.png)

- But if we use the url, we can see which user is logged in, this means there is IDOR vulnerability, so we can change the user filed value from guest to admin and see.

![image](https://user-images.githubusercontent.com/54020728/217137799-3899985a-8e7d-4008-bddf-0b6da8591b99.png)

- Vola! We are login in as admin and there's the flag.
- 
![image](https://user-images.githubusercontent.com/54020728/217136268-e1a93a13-866f-4283-a644-dfb08941042d.png)

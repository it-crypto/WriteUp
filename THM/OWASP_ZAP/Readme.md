# OWASP ZAP

* OWASP ZAP is a open source and free, its similar to burp suite but in these there are no paid versions. All the features can be used by the user.
* OWASP Zap is a security testing framework much like Burp Suite. It acts as a very robust enumeration tool. It is used to test applications.

* Basics
* Automated Scan : It performs both passive and automated scans to build a sitemap and detect vulnerabilities.

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/286717d1-8eb6-4c71-a90b-78cefe540fc8)

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/5338b4f8-c1a2-40d6-b7d2-6af4bf0b2424)

* Attack started and it is enumerating all the directories and finding if there is any attacks possible
* Before logging in

    ![image](https://github.com/it-crypto/WriteUp/assets/54020728/26a36384-53be-457f-8b3f-40c156fdb27b)

* Connecting proxy

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/227036d0-5f16-4998-9615-f44e363d9457)

* Save the SSL certificate from the ZAP options and import the certificate in the browser(firefox) and add that we trust the certificate.
* Here I am using FoxyProxy tool for intercepting and modifying the requests.
* Then login into the DVWA application and from the security tab set the level to low.
* From the Inspect tab you can find the PHPSessionID
* Now got to ZAP add HTTP sessions and check for the PHPSessionID which we found earlier and set as active.
* Now re-run the scan again.

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/c0fe7b11-3d5d-41da-841f-1b3241bff67a)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/8b6c280e-4fa5-4383-88e2-ea3a3b69708b)
  
* Using wordlists to enumerate

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/7d20365f-7bb0-458c-b444-4f92e4f52567)

  ![image](https://github.com/it-crypto/WriteUp/assets/54020728/f74608ab-3855-4380-b007-5779f1611f00)

* Using brute force to get the credentials

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/f0e27098-8aa2-4e82-9c77-8d551dfa9a72)

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/8a898ad6-81eb-42eb-a482-db408712f9d6)

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/bc8be3fd-21bd-472b-981b-16ffef02336c)

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/23ea39ec-3e72-4027-bcba-55f8f889cdfd)

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/d3ceee19-455a-4603-a61f-53c1ba7a1646)

   ![image](https://github.com/it-crypto/WriteUp/assets/54020728/3521a81f-564a-4a4c-9f58-6f6fc80d0230)

* We can add different extensions from markertplace and enable them so that they will be used in scanning to find more vulnerabilities.  

  


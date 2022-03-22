# Day-7 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://faiyazhacks.medium.com/story-of-an-encoded-xss-e83c7ea9e02
- https://faiyazhacks.medium.com/how-i-got-my-second-swag-2fa08a1dfd39
- https://faiyazhacks.medium.com/hacking-my-isp-for-free-internet-12d8ddad492

#### Learned:

1. From Article 1:
      - Try to find some hidden parameters using some tools like FFUF and Paramspider.
      - Then i thought let’s URL Encode the special characters and see what happens after. I encoded < to %3c and > to %3e and to my surprise it got rendered.
      - It seems like the back end was checking some of the harmful tags to prevent xss. After sometime, i found that when i add “/” in the payload, it triggers the WAF and redirects me to the NotFound page.
      - By analyzing the web page behavior, I concluded that we cannot use any tags since it will block us right away. So our only target is javascript events like onmouseover, onclick etc.
      - Final Payload: `batman“ onmouseover=alert(1)>`.

2. From Article 2:
    - Found a Parameter using gau: `https://www.vulnerabledomain.com/registration.aspx?source=/dashboard`.
    - After attempting the few payload, I thought that maybe this site is only allowing internal redirections.
    - I tried `https://www.vulnerabledomain.com/registration.aspx?source=https://vulnerabledomain.com` and to my surprise, it worked!
    - `https://vulnerabledomain.com/registration.aspx?source=https://vulnerabledomain.com.bing.com/` which successfully redirected me to bing.com!

3. From Article 3:
    - Using masscan to find the ip of the ISP: `masscan 172.x.x.128 -p80,443,21`.
    - Basically, i was looking for some http/https and ftp services. After scanning completed, i found couple of ip that have those ports open. I found many cctv cameras and to my surprise I also found around 20 routers running http/https services. Then i immediately tried to login into those routers with default credentials and BOOM!!!! I got logged in and there i found PPPoE credentials.

### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room Of **RustScan && Nessus** : https://tryhackme.com/room/rustscan , https://tryhackme.com/room/rpnessusredux

### 3. PortSwigger Labs: [DONE]

 - [X] **Access control vulnerabilities (11/13)**
 -  Lab: URL-based access control can be circumvented  (https://portswigger.net/web-security/access-control/lab-url-based-access-control-can-be-circumvented)
 -  Lab: Method-based access control can be circumvented  (https://portswigger.net/web-security/access-control/lab-method-based-access-control-can-be-circumvented)

### 4. Youtube Video: [TODAY TIRED AF HAVEN'T WATCHED ANYTHING]

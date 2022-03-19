# Day-4 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://medium.com/@vamshivaran110/my-first-blind-sql-injection-7db4b5e5c66d
- https://medium.com/@vamshivaran110/full-account-takeover-due-to-improper-validation-of-old-password-d4b9f4eec3f8
- https://medium.com/@vamshivaran110/sensitive-information-disclosure-through-unrestricted-directories-82b720994f36

#### Learned:

1. From Article 1:
      - Blind SQL Injection Payload: 0'XOR(if(now()=sysdate(),sleep(20),0))XOR’Z (* is replaced with any seconds ).
      - Always Crawl your Host with Burp Suite.
      - After Crawling send Endpoints to Repeater tab and apply different different types of SQL Payloads and check Response time.

2. From Article 2:
    - Fired up burp and intercept the password changing request, the request body only contains the New password parameter and there is No Validation mechanism for checking the old password. Hence we can successfully change the new password without entering Correct old password.
    - Attacker Scenario: Intercept the Victim trafic and change the request to password changing request, and enter new password. Since there is no validation of old password attacker directly change the victim account password and gain full access.

3. From Article 3:
    - (.git) directory exposing many sensitive information.
    - found (.git) directory using fuzzing with ffuf.
 
 ### 2. TryHackMe Labs: [DONE]

- [X] Solved Complete Room Of **REmux The Tmux && OWASP ZAP** : https://tryhackme.com/room/tmuxremux , https://tryhackme.com/room/learnowaspzap

### 3. PortSwigger Labs: [DONE]

- [X] **Access control vulnerabilities (3/13)**
 -  Lab: Unprotected admin functionality (https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality)
 -  Lab: Unprotected admin functionality with unpredictable URL (https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality-with-unpredictable-url)
 -  Lab: User role controlled by request parameter (https://portswigger.net/web-security/access-control/lab-user-role-controlled-by-request-parameter)

### 4. Youtube Video: [DONE]

- Watched : OrwaGodFather Part 4 Video : (https://www.youtube.com/watch?v=_aST_z_qTYE&t=890s)

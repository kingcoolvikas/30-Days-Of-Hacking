# Day-10 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://medium.com/@tobydavenn/how-i-was-able-to-takeover-any-account-on-one-of-europes-largest-media-companies-e8d25e59c08
- https://medium.com/@elqayserelqayser/account-takeover-via-reset-password-apple-corp-784699fb1392
- https://mukibas37.medium.com/information-disclosure-bug-78907c5d49fc

#### Learned:

1. From Article 1:
      - While testing functions, I noticed on the reset password (this is not a reset password takeover) an endpoint that reflected my UID, this was around 32 characters long.
      - There was a group feature on the site. When requesting to join a group, adding .json onto the endpoint revealed all UIDs of members within the group.
      - Adding these UIDs to the changeEmail endpoint revealed all PII associated with the account, even password hashes.
	  - I remembered the endpoint that allowed me to change my profile information took my UID and email address to verify what account was being changed.
	  - Changing the UID and email address to that of a valid account allowed me to change all information, including password of a victim account.

2. From Article 2:
    - I start doing recon but not for the main domain but for the corp domain and filtered with httprobe and hakrawler to get status code for each then check every one of them I found one those has login page let’s examine it.
    - I brute force and It’s has no rate limit so that can lead to account takeover if you get the right user and password you can change it immediately.
    - Then I reported the vulnerability to Apple and Got HOF.

3. From Article 3:
    - Information disclosure vulnerability is the leakage of sensitive information to its users. If this bug is present in any of the web applications it may leak sensitive data to an untrusted user.
    - Information disclosure bugs severe impact based on the severity of the information. For example, a particular organization holding customer records by mistake due to inappropriate misconfiguration data would leak into the wrong hands.
    

### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room Of **WebAppSec 101** : https://tryhackme.com/room/webappsec101

### 3. PortSwigger Labs: [DONE]

 - [X] **Information disclosure (1/5)**
 -  Lab: Information disclosure in error messages    (https://portswigger.net/web-security/information-disclosure/exploiting/lab-infoleak-in-error-messages)

### 4. Youtube Video: [DONE]

- Watched WP_scan by Intigriti (https://www.youtube.com/watch?v=XSSyE4IWs1I)

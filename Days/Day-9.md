# Day-9 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://wahaz.medium.com/broken-authentication-and-idor-at-redacted-646de8d508e6
- https://medium.com/@harishhacker3010/how-i-hacked-nasa-to-execute-arbitrary-commands-in-their-server-29d44292a60a
- https://naveenroy008.medium.com/tale-of-a-misconfiguration-in-password-reset-e8fb484a4661

#### Learned:

1. From Article 1:
      - After getting the subdomin, I try to open and see one by one of them, then get one of the interesting subdomain that show the login page, I guess the login page was for the admin panel.
      - So I try to check the source code with inspect element, surprisingly it’s totally different. There is redirect code in the client side `<script>window.location=”/login”;</script>`.
      - Comment the redirect code, then open the source code locally. Then voila the admin panel is shown. But ofc the data is can’t load, because the CSP (Content Security Policy).
	  - After that go deeper to the javascript source code. There is some javascript file included, and found some endpoint that interesting to test. After test some endpoint there is one endpoint vulnerable with IDOR. `https://admin.redacted.com/User/deleteImage` Just give deleteImage id and the image will be deleted, Thus IDOR Confirmed.

2. From Article 2:
    - I used an extension called wappalyzer for firefox, Once I started to open live websites of NASA, wappalyzer showed me that NASA is using drupal as their CMS. then I found that website using an outdated drupal which is vulnerable to CVE-2018–7600.
    - Found Using, Drupwn.py tool. Then I tried to exploit that vulnerability it worked Boom!.
    - Then I reported the vulnerability to their security email `(vulnerability-report@nasa.gov)`.

3. From Article 3:
    - This post is about a misconfiguration in password reset I found on a popular help desk software sometimes ago where they were leaking the reset token. And guess what? This was not in the Referer header :D but right in the response of the request itself.
    - Notice the auth_token? Yes! That’s the reset token you would receive in email on a valid password reset request. And the format of the password reset link was: `https://[team_name].redacted.com/Auth/ResetPassword/[auth_token]`.
	- Always check response to requests whenever you expect to receive a token in email.

### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room Of **FFUF** : https://tryhackme.com/room/ffuf

### 3. PortSwigger Labs: [DONE]

 - [X] **Access control vulnerabilities (13/13)**
 -  Lab: Referer-based access control    (https://portswigger.net/web-security/access-control/lab-referer-based-access-control)

### 4. Youtube Video: [DONE]

- Watched JWT_Tool.py by Intigriti (https://www.youtube.com/watch?v=ZGarKE9KTAY)

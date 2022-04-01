# Day-17 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://medium.com/@vivekkashyap0707/my-first-rce-from-n-a-to-triaged-cve-2021-3064-acdd0541c664
- https://medium.com/@rupachandransangothi22/host-header-injection-leads-to-pre-account-takeover-worth-100-1bd8f2d51876
- https://medium.com/@sonawanerushab400/story-of-instagram-open-redirect-fdadf64a1c

#### Learned:

1. From Article 1:
      - I searched that target on shodan, crt.sh, security trials. I search with these keywords on shodan Ssl:”target Inc.” 200 , target(.)com on crt.sh & security trials.
      - after digging a little much I saw three very long sub-domain let me just show you guys a example `“https://sns-snsvpn.nme.bllon.sns.target(.)com/global-protect/login.esp”`.
      - Then I started digging at this sub-domain and fortunately saw that it is managed by palo alto services. And the version was clearly visible on shodan.
      - Then I immediately searched on Google Pan-OS 8.1.15 vulnerabilities. After few hours I came at a conclusion that I got a gem in Cole mine, I got a Github Poc thats conclude that it is a RCE.	
     
2. From Article 2:
    - Navigate to https://accounts.test.target.com/users/add and Enter the Victim’s Email address and Random First name and Last name to get the Invitation Link.
    - Capture this request using the Burp suite and send the request to Repeater. 
    - Add Host: evil.com instead of Host: accounts.test.target.com in the Repeater Request. Then Click Go and Check the Response.
    - After this, check your(victim’s) email. You got an email of Invitation(Add) user with the token. Which looks Like : `https://evil.com/login?resetpassword&username=bugbountyhunter8682%40gmail.com&expiration=-1&token=228fbccde55f3ae720513af710d5e1404dad3a2f#reset-password`.
    - When an attacker opens the link by inserting subdomain and domain name as accounts.test.target.com instead of evil.com with same paramters and token value BOOM It Works!!!. Set Password page appears, Clear Pre-Account Takeover.

3. From Article 3:
    - Let’s get started, you need to have the URL of the application that allows image rendering. The GET parameter called url is responsible for indicating the path of an image to be rendered.
    - I added my profile photo URL from Github. SVG uses the XML language to create graphics and drawings, like those graphics that we see in reports on websites. We can use it to write javascript code and make the server execute it.
    - On the third line it will create a green circle with the size 50x50 and then it will execute the javascript code. Let’s copy it and create an SVG file and paste the contents into the file and close. I opened the terminal in the directory where the file was, opened port 80 HTTP and made port forwarding using Ngrok, then copy the URL with the path of the image and pasted in the value of the url parameter of that application. We achieved!!! The javascript code was rendered and we got the alert.


### 2. TryHackMe Labs: [HALF DONE]

 - [X] Solved Task:1,2,3,4,5,7 Of **Crack The Hash Level 2** : (https://tryhackme.com/room/crackthehashlevel2)

### 3. PortSwigger Labs: [DONE]

 - [X] **Authentication (3/14)**
 -  Lab: Password reset broken logic   (https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-reset-broken-logic)

### 4. Youtube Video: [DONE]

- Watched Confidential Document (Sensitive Data Exposure) [OWASP JUICE SHOP] (https://www.youtube.com/watch?v=Yi7OiMtzGXc)

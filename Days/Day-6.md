# Day-6 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://debprasadbanerjee502.medium.com/adobe-bug-bounty-using-idor-confidential-data-leaks-f6c55e5143d0
- https://debprasadbanerjee502.medium.com/what-ive-learned-from-hunting-bugs-for-2-months-dd982010347e
- https://debprasadbanerjee502.medium.com/how-i-hacked-iit-k-41653cc2fec4

#### Learned:

1. From Article 1:
      - Collect Endpoint and exclude images and other stuff using this command: `cat adobe.txt | gauplus — subs -b png,jpg,gif,jpeg,swf,woff -o adobeurl.txt`.
      - Then find which is live or not using this simple command : `cat adobeurl.txt | httpx -mc 200 >> finalurls.txt`.
      - I visit the document URL, now I find a usual document, nothing interesting but then i looked at the URL, it had document/200, I changed that 200 to 201 but nothing happened so maybe no IDOR? I sent the request to burp>Intruder> use 100–1000 as payload set and fuzz the document/$200$, BOOM! here's the response. But now the question is, are the files really confidential? So turns out yes, not only documents but highly critical internal data is also leaked.

2. From Article 2:
    - Don’t select popular targets, Don’t waste time on a 20 hour course.
    - Try smarter and not harder. Learn only one vulnerability at a time and look for it in a wide-scope program. Stop with ready made methodologies.
    - Set up your testing machine, with tools and keep proper notes on how to use them. Learn to use it automatically on several hosts at once.
    - >Excellence is not a gift but a skill that takes practice — Plato.

3. From Article 3:
    - Add This Endpoint in your wordlist : `getbrochure.htm`.
    - After getting into this Endpoint got an Error : HTTP Status 400 - Required int parameter 'course_code' is not present.
    - So added : getbrochure.htm?course_code=1111 in GET url.
    - And Just FUZZ the Number in Burp Suite INTRUDER Tab which got confidential datas.

### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room Of **Toolbox: Vim && Phishing | Hidden Eye** : https://tryhackme.com/room/toolboxvim , https://tryhackme.com/room/phishinghiddeneye

### 3. PortSwigger Labs: [DONE]

 - [X] **Access control vulnerabilities (9/13)**
 -  Lab: User role can be modified in user profile  (https://portswigger.net/web-security/access-control/lab-user-role-can-be-modified-in-user-profile)
 -  Lab: User ID controlled by request parameter, with unpredictable user IDs  (https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-unpredictable-user-ids)

### 4. Youtube Video: [FULL DONE]

 - Watched : BittenTech HTTP Security Headers | Content Security Policy (CSP) | Strict Transport Security (HSTS) : (https://www.youtube.com/watch?v=8_nfQAdWELU&t=1148s)

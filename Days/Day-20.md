# Day-20 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://amit-lt.medium.com/multiple-times-i-hacked-duke-university-with-rxss-vulnerability-7e291aad043a
- https://amit-lt.medium.com/hacked-nokia-with-reflected-cross-site-scripting-vulnerability-327daa8e62fb
- https://amit-lt.medium.com/scenario-of-reflected-cross-site-scripting-vulnerability-a3ee189dd822

#### Learned:

1. From Article 1:
      - Now first of all start with Google Dorks & always start with these dorks, `site:*.duke.edu inurl:/login`
      - I discovered a Forget password functionality there is another function which is called Account Lookup sometimes forget pwd functionality is not properly working whereas the Account Lookup function will properly be worked.
	  - Then I entered `xss<>` into Legal First/Given Name & Legal Last/Family Name. And my name got reflected in response body without sanitizing properly.   
     - Then i enter this simple payload: `'"><script>alert(document.domain)</script>'` and i got a POP UP.	
 
     
2. From Article 2:
    - I started from Google Dorks, `site:*nokia.com inurl:/login.jsp?msg=`. And I discovered my target url.
    - Simply I entered script tag into message parameter like this `<script></script>` and in response it got reflected.
    - so i crafted a payload : `<IMG%20SRC=”https://d15shllkswkct0.cloudfront.net/wp-content/blogs.dir/1/files/2011/08/nokia-hacked.png"><h1>Too%20Weak%20Security</h1>` and i can clearly see the image in the vulnerable page.


3. From Article 3:
    - Suddenly in my target application, I discovered two parameters where I have to enter my address so that for basic tags I used this: `Xss<>`.
    - Now I opened Inspect Element tab and I was shocked that my `Xss<>` doesn’t sanitize properly, Instantly I crafted a Payload which is an image source `<img src=xss onerror=alert(document.domain)>`. I got a beautifl Pop up.
    - And always remember during testing for XSS vulnerabilities if there was multiple parameters the test like this
Parameter 1:
`<img src=xss onerror=alert(1)>`
Parameter 2:
`<img src=xss onerror=alert(2)>`
If any parameters are vulnerable then the pop-up indicates the alert number.


### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room On **Crack The Hash Level 2** : (https://tryhackme.com/room/crackthehashlevel2)

### 3. PortSwigger Labs: [DONE]

 - [X] **Authentication (6/14)**
 -  Lab: Broken brute-force protection, IP block   (https://portswigger.net/web-security/authentication/password-based/lab-broken-bruteforce-protection-ip-block)

### 4. Youtube Video: [DONE]

- 2FA bypasses: Logical Thinking for contexts By Aditya Shinde On Securzy (WAS A ZOOM MEETING)

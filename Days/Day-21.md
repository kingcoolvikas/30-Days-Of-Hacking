# Day-21 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://systemweakness.com/introduction-to-csrf-how-can-a-cookie-get-you-hacked-1-2-d34e0a0e6319
- https://shubhangivashist.medium.com/introduction-to-csrf-stepwise-guide-to-bypass-csrf-tokens-2-2-1375b30d479e
- https://medium.com/@cyberxprite/an-interesting-rate-limit-bypass-2d4728699f71

#### Learned:

1. From Article 1:
      - A cookie has three purposes, session management, personalization, and tracking, it is an assistant to the webserver that works in collaboration with the browser to make your life better. But when the web application solely relies on cookies for session management, the attacker can perform the infamous CSRF attack.
      - CSRF is a Client-side vulnerability i.e., If an application is vulnerable to CSRF, the attacker can use any social engineering method on the authenticated user and force him to execute an unwanted action on the web application. Now when this authenticated user is a “privileged user”, the attacker can compromise the entire application easily.
	  - 1. Attacker sends an innocuous-looking web page to the authenticated user (using social engineering). 
```
<html>     
   <body>         
      <form action="https://jackswebsite.com/update" method="POST">             
         <input type="hidden" name="email" value="dark@hack.com" />  
         <input type="submit" value="automated" />       
      </form>        
      <script>             
          document.forms[0].submit();         
      </script>     
    </body> 
</html>
``` 
     - 2. Now as soon as the user visits the web page it will trigger an HTTP request to Jack’s website (which is vulnerable to CSRF). This is a forged request to change the user mail ID to dark@hack.com
     - 3. As the user is authenticated into Jack’s website, the browser will automatically add the session cookie into the request, regardless of the request’s origin (partly circumventing the same-origin policy)
     - 4. Once the HTTP request is sent, Jack’s website will process it normally and will update the user mail ID to dark@hack.com. The attack has been executed successfully.	
 
     
2. From Article 2:
    - GUIDE TO EXPLOIT CSRF TOKENS.
    - 1. **OMIT THE CSRF TOKENS**. In step 1, we will omit the CSRF token and see if the request goes through. Some web apps validate the CSRF tokens when they are present, but when not present, it doesn’t even bother to look for them (inconsiderate much?).
    - 2. **CHANGE REQUEST METHOD FROM POST TO GET**. In step 2, we will change the request methods from POST to GET and omit the CSRF token from the GET request. This task can be easily done using the Repeater plug-in in Burpsuite but it can also be done manually.
    - 3. **USE ANOTHER USER’S CSRF TOKEN**. In step 3 all we need to do is to replace the CSRF token in the request with another valid CSRF token, and it will be validated!
```
<html>     
   <body>         
      <form action="https://jackswebsite.com/update-mail">             
        <input type="hidden" name="email" value="dark@hack.com" /> 
        <input type="hidden" name="csrf" value="hackersCSRFtoken" />
        <input type="submit" value="automated" />       
      </form>        
      <script>             
          document.forms[0].submit();         
      </script>     
    </body> 
</html>
```
    - 4. **THE CLASSIC CASE OF DOUBLE SUBMIT COOKIE**. An alternative validation method used by some web servers is the double submit cookie method. This technique is stateless, i.e., the server is not keeping any record for the CSRF tokens! In fact, the CSRF token is merely a copy of the session cookie.
```
POST /account/update-email HTTP/1.1
HOST: jackswebsite.com
Cookie: session=abc12345efGxyZ
.
.
other headers 
.
.
email=jack%40jack.com&csrf=abc12345efGxyZ
```


3. From Article 3:
    - For all beginners, I would suggest whenever you try to find bugs in the website, you must try rate limit vulnerability, which is easy to find & more comfortable.
    - 	Last night, i was looking for vulnerabilities in a program and i got nothing to report, then i test for rate limit vulnerability
As usual, I start with rate limit on forget password endpoint.
But it was protected with rate limit. Then I decided to bypass it.
    - So I tried following bypass :
```
X-Forwarded-For: IP 
Then I tried all of below,
X-Originating-IP: 127.0.0.1
X-Forwarded-For: 127.0.0.1
X-Remote-IP: 127.0.0.1
X-Remote-Address: 127.0.0.1 (No luck this is secure)
```
    - I got frustrated and put all the above headers to Intruder Selected $1$ from IP address(127.0.0.1) as position and Attack to all of them, And then i noticed i got 200 status code for all i.e. The Rate Limit was Bypassed with :
```
X-Forwarded-For: 127.0.0.1
X-Forwarded-For: 127.0.0.2
X-Forwarded-For: 127.0.0.3 so on…
```
So basically the Rate Limit was bypassed by changing the IP in X-Forwarded-For Header :)

### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room On **Spring4Shell** : (https://tryhackme.com/room/spring4shell)

### 3. PortSwigger Labs: [DONE]

 - [X] **Authentication (7/14)**
 -  Lab: Lab: Username enumeration via account lock   (https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-account-lock)

### 4. Youtube Video: [DONE]

- How To Hunt: Cross-Site Request Forgery (CSRF) - Kathan Patel (https://www.youtube.com/watch?v=9eIUfCXyRgE)

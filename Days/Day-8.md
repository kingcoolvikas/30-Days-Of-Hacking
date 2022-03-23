# Day-8 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://faiyazhacks.medium.com/i-d-o-r-to-account-takeover-834371d2365a
- https://faiyazhacks.medium.com/unrestricted-file-uploads-e361639913b1
- https://faiyazhacks.medium.com/first-bug-bounty-account-takeover-3b2c4ba9e091

#### Learned:

1. From Article 1:
      - Vulnerability that can directly result in Account Takeover. For that, I started testing two main things of the webpage: Login flow of the web application, Password Reset flow of the web application.
      - And i found a endpoint: `/home/reset/user_id/reg`
      - Which is used to change the user’s password. So here i tried to modify the user_id to other user’s id and BOOM! I was able to reset the password of that other user. How Easy!

2. From Article 2:
    - A ebook platform having the following functionalities: Login/Signup, Create Stores, Forget Password.
    - On digging deeper, i found that there is a feature to add logo in your store. So i tried to upload a html file to see if i can actually upload files other than images. And guess what? I failed.
    - After that, i created an html file and saved as `anything.png` and tried to change the extension back to html using burpsuite.
    - And Now i tried to upload the file again and this time it worked!!! The html file got uploaded successfully.

3. From Article 3:
    - Login functionality of the Web app: We can create accounts using phone numbers as well as email.
    - If we try resetting our password, if the user has created an account using phone number then an otp will be send to that number else the otp will be sent on the email.
	- After analyzing this two things, i fired up burpsuite to see what is going behind the scene and found that if we try resetting our password an extra parameter(customer_email) is also sent to the server.
	- After seeing this, i tried to add my email that parameter and guess what….the otp got sent to both customer_email an customer_mobile. Thus Account takeover.

### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room Of **Tshark** : https://tryhackme.com/room/tshark

### 3. PortSwigger Labs: [DONE]

 - [X] **Access control vulnerabilities (12/13)**
 -  Lab: Multi-step process with no access control on one step   (https://portswigger.net/web-security/access-control/lab-multi-step-process-with-no-access-control-on-one-step)

### 4. Youtube Video: [DONE]

- Watched Arjun Tool by Intigriti: (https://www.youtube.com/watch?v=wRPxbz_Ht3k)

# Day-18 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://pawanchhabria.medium.com/how-i-accessed-the-sensitive-document-which-i-had-already-deleted-adbc1e6fbb25
- https://pawanchhabria.medium.com/my-first-pre-auth-account-takeover-in-20-secs-7c90fd273ffa
- https://pawanchhabria.medium.com/how-i-was-able-to-access-a-properly-configured-s3-bucket-a0e949446341

#### Learned:

1. From Article 1:
      - I came across an application where it had an option of uploading documents for KYC. Aadhar Card, PAN Card, Driving License and Passport were the documents that can uploaded on the website. There documents are “Sensitive” in nature and utmost care must be taken while handling them.
      - I tried uploading a dummy image and captured the request. Once the image got uploaded, the server returned a success response with the link of the uploaded image.
	  - The image was getting uploaded on some S3 bucket. I tried accessing URL And BOOM the document was accessible publicly. Imagine if some one might have uploaded their “Passport” or “Other Sensitive” document.
     -  In the frontend it showed me the uploaded document. Then, I thought, lets try to delete the document and check whether it gets deleted from the UI only or gets deleted from the server as well. After Deleting the Document i again go to same url and found out that i can still able to view the document. This is a serious Business Impact and Privacy Issue bug here .	
     
2. From Article 2:
    - Forgot Password is the best possible feature where most of the “Pre-Auth” account takeovers happen, so I started playing around with it.
    - I initiated a “Forgot Password” request with victim’s email id. It was only accepting “email_id” as the parameter and if correct email id is provided, the application sends an OTP to the registered mobile number. 
    - Then, there was a “Resend OTP” feature which caught my attention. I initiated a “Resend OTP” request and captured it with “Burp Suite”. 
    - There was a mobile number parameter which was being passed, and it was the registered mobile number on which OTP is received. So, I modified the value of “mobile_no” parameter to my mobile number and forwarded the request.
    - And Guess what, I received the OTP on my mobile number, I entered the OTP and tried to reset the password. The application gave a success message. I tried to login with the victim’s email id and the password which I had set, and the application allowed me to login, lol.

3. From Article 3:
    - I came across an application which was using “S3 Buckets”. The bucket was used to store “KYC” documents and other important stuff. I tried accessing the bucket with “AWS CLI” to check for “Public Read” and “Public Write” access. Fortunately, the bucket was properly configured and gave the error as “Access Denied” for both “Public Read” and “Public Write”.
    - Got to know about a extension BurpSuite-Xkeys — A Burp Suite Extension to extract interesting strings (Keys, API keys, Secret tokens, AWS Secrets etc.)
    - As soon as I started getting the results, “aws_secret_access_key” and “aws_access” caught my eyes. These things were present in a config file which was available without authentication. The config file had all the important stuff that the developer had left by mistake.
    - I configured “AWS CLI” with AWS Access&secret key and tried accessing the bucket. And BOOM, The bucket listed the content, and I could access all the “KYC Documents”. Not only this, but the bucket also allowed me to upload and delete the content.


### 2. TryHackMe Labs: [HALF DONE]

 - [X] Solved 2 More hashes Of **Crack The Hash Level 2** : (https://tryhackme.com/room/crackthehashlevel2)

### 3. PortSwigger Labs: [DONE]

 - [X] **Authentication (4/14)**
 -  Lab: Username enumeration via subtly different responses   (https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-subtly-different-responses)

### 4. Youtube Video: [DONE]

- Watched FIND HIDDEN PARAMETERS WITH PARAMINER (https://www.youtube.com/watch?v=oUuz242c92M)

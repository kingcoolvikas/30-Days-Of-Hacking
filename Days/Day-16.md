# Day-16 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://medium.com/@sonawanerushab400/how-i-found-rxss-on-cedars-sinai-this-is-good-story-but-sad-ending-426cfafdd701
- https://medium.com/@sonawanerushab400/open-redirect-on-third-party-21b58daeb088
- https://medium.com/@sonawanerushab400/story-of-instagram-open-redirect-fdadf64a1c

#### Learned:

1. From Article 1:
      - After some research i got the domain with `biomanufacturing.cedars-sinai.org` i started to testing on their page i noticed there is one input field with search funtion i was entered an xss payload right there but haven't got pop-up.
      - But i noticed the characters in front of the double quote is out of the input field and before the quote have some backslashes. Then i right click on my mouse and inpected the element and what i see the all material of the input is getting executed in html code.
	  - So i quickly started to bypass it. Inside the search bar most of all event is not working so i used “onmouseover” and after bypassing it my payload looks like this : `helloworld” onmouseover=prompt(1) test=”`	
     
2. From Article 2:
    - I was started the journey of this bug with 8x8 program from hackerone. I saw the program old bugs and did some research like reading old bug how they find the vulnerabilities on this program how they exploited it. Normally i understand how the website actually works.
    - After tesing a long time on website. I found one page with login info. The website is not allowing us to disclose the name of subdomain therefore we would call it nomore.8x8.com.
	- Then, I thought to why not to find open redirect. I opened my cmd and started `Arjun` tool to find parameter. I found one parameter like “nextPage” . I quikly tried to bypass it and i was successful. Url looks like `https://nomore.8x8.com/?nextPage=%2F%2F%2Fwww.google.com`.

3. From Article 3:
    - After login into instagram there was a two options like “Save Info” and “Not Now’. If i were click on anyone i was redirected to instagram.com.After thinking on that i was return come to that link and that’s link looking like this : `https://www.instagram.com/accounts/onetap/?next=%2F`.
    - `?next=%2F%2F%2Fwww.google.com`
    - `?next=%2F%2Fhttps%3A%2F%2Fwww.google.com%2F`
    - `?next=%2F%5C%2F%5Chttps%3A%2F%2Fwww.google.com%2F`
    - I took a lot of time to do this but it was very easy and final payload looks like this 😂😂😅 : `?next=https%3A%2F%2Fwww.google.com%2F`
    - If i will send this link to someone and they will click on “save info” or “not now” they will be redirect to another website.


### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room Of **Crack The Hash** : (https://tryhackme.com/room/crackthehash)

### 3. PortSwigger Labs: [DONE]

 - [X] **Authentication (2/14)**
 -  Lab: 2FA simple bypass   (https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-simple-bypass)

### 4. Youtube Video: [TODAY TIRED AF HAVEN'T WATCHED ANYTHING]

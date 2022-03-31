# Day-14 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://vamshi-vemula.medium.com/how-i-got-my-first-bounty-open-redirect-80832e5bf4e6
- https://medium.com/@sudhanshur705/story-about-my-first-bug-bounty-9fe710be8241
- https://shambhavishandilya.medium.com/linux-commands-to-have-fun-on-terminal-2df8da483d59

#### Learned:

1. From Article 1:
      - I was testing every functionality which redirects me to the login page of that website. After a lot of manual work, The website has a deals page, To activate the deal user should be logged in. Then I tried to click on the login button. It redirects me to the login page `example.com/login?param=/deals` something like that. It has a redirect parameter that redirects me to that page when I successfully log in.
      - I tried with different open redirect payloads and bypassing mechanisms. You can get Open Redirect cheatsheet from `https://pentester.land/cheatsheets/2018/11/02/open-redirect-cheatsheet.html`. After some modification and lots of trying… Boom! I found the open redirect vulnerability.
	  - Immediately I reported the Vulnerability to the Security team of the website. After 3 weeks I received a response from their team as they accepted my report and they will provide me a bounty for my finding. I received my bounty reward from the company after a week.

2. From Article 2:
    - so I started looking for ucweb.com subdomains here and found this subdomain `samsung.ucweb.com`, samsung ahh let’s see what’s there.I opened that subdomain and got this 403 Forbidden.
    - So that’s what I did I used this simple dork site:samsung.ucweb.com and the results really suprised me.
	- I opened this url `http://samsung.ucweb.com/webstore/classify.html?dataKey=LifeStyle&title=LifeStyle` and started testing the parameters , the title parameter was reflecting the input so for checking if there is any filter or something I used <b></b> and found out that there was no filter.
    - I used the payload `<script>alert(1)</script>` but it didn’t work then I tried `"><img src=x onerror=alert(‘XSS’)>` and boooom yeah the I got the xss popup.
	 - The 2nd xss I found this month only, in the same domain.For fixing the previous xss they removed that endpoint and if I try to open that endpoint now I will get a 404 error not found.
	 - After some days I got to know about dirsearch,so I thought of giving it a try and it was working perfectly , from the result I got one more endpoint `/test/`.
	 - I opened `http://samsung.ucweb.com/test/` and from here I found this `http://samsung.ucweb.com/test/classify.html?dataKey=New&title=` same url just like before, I used the payload and yeah you guess it right the xss popup was there.

3. From Article 3:
    - cmatrix : `sudo apt install cmatrix`.
    - xcowsay : `sudo apt install xcowsay`.
    - sl : `sudo apt install sl`.
    - aafire : `sudo apt install libaa-bin`.
    - asciiquarium : `snap install asciiquarium`.
    - xeyes : `sudo apt install x11-apps`.
    - asciiview : `sudo apt install aview`.
    - yes : `sudo apt install yes`.
    - fortune : `sudo apt install fortune`.
    - banner + lolcat : `sudo apt install lolcat`, `sudo apt install sysvbanner`.

    

### 2. TryHackMe Labs: [HALF DONE]

 - [X] Solved Half Room On **Brute It** : (https://tryhackme.com/room/bruteit)

### 3. PortSwigger Labs: [DONE]

 - [X] **Information disclosure (5/5)**
 -  Lab: Information disclosure in version control history  (https://portswigger.net/web-security/information-disclosure/exploiting/lab-infoleak-in-version-control-history)

### 4. Youtube Video: [TODAY TIRED AF HAVEN'T WATCHED ANYTHING]

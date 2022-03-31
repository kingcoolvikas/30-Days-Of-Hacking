# Day-12 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://medium.com/@awezkagdi.ak/an-clickjacking-which-rewarded-me-with-275-719e0f49bf96
- https://medium.com/@Infected69/xss-using-response-manipulation-42812467fa6c
- https://cyb3rwulfengrav.medium.com/one-month-bug-bounty-journey-update-9f6f0e3549d2

#### Learned:

1. From Article 1:
      - Today we will discuss about the clickjacking Vulnerability which rewarded me with 275$. Yes you read that correct. This was obviously an private hackerone program.
      - `<html> 2 <head> 3 <title>Clickjacking Test</title> 4 </head> 5 <body> 6 <p>If you can see the website below, it’s vulnerable to clickjacking.</p> 7 <iframe src=”https://example.com/account" width=”500" height=”500"></iframe> 8 </body> 9</html>`
      - Always perform clickjacking on sensitive pages (password change, email change, any profile update etc.)

2. From Article 2:
    - So I was searching for a responsible disclosure program and after some Google Dorking, I got one. Because the program doesn’t allow public exposure let us consider the domain as vulndomain.com.
    - I did some subdomain-finding and got my first URL for testing. It was a helpdesk kinda page where there was a search option. After some directory enumeration and functionality checks, I noticed user input getting reflected on the index page of the subdomain.
    - As I already described that the server was validating and sanitizing the client-side inputs and Requests, So I started seeking Responses and got the right spot.

3. From Article 3:
    - When I started out I had run across a few web application testing checklists and thought that was a great way to start. The one I found to be most helpful is by six2dez and is located at `https://github.com/six2dez/pentest-book/blob/master/others/web-checklist.md`.
    - I know a lot of bug bounty hunters suggest picking a program that is wide scope and you can hunt on it longer. While there is indeed many benefits to this I feel like this approach is likely to be less successful to new hunters than in their times where there was much less competition. But I also believe having two to three programs to focus on is the best approach and that picking one with a large scope is in fact a good idea still.
    - Manually picking a target or targets to test on for an extended period of time and diving in to your favorite learning resource (portswigger, pentesterlab, bugbountyhunter, etc.) will be the best path to finding undiscovered high impact vulnerabilities. If you are able to put all your time into this method without feeling burned out it is probably the best choice to focus most if not all your energy.

    

### 2. TryHackMe Labs: [HALF DONE]

 - [X] Solved 11 Questions On **Wifi Hacking 101** : https://tryhackme.com/room/wifihacking101

### 3. PortSwigger Labs: [DONE]

 - [X] **Information disclosure (3/5)**
 -  Lab: Source code disclosure via backup files    (https://portswigger.net/web-security/information-disclosure/exploiting/lab-infoleak-via-backup-files)

### 4. Youtube Video: [TODAY TIRED AF HAVEN'T WATCHED ANYTHING]

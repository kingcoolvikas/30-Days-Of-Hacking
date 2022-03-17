# Day-2 (30-Days-Of-Hacking)

### 1. Read 3 Article:

- https://xkurtph.medium.com/how-i-access-other-domains-in-infinityfree-net-using-directory-traversal-4625692d6a2d
- https://medium.com/@tobydavenn/how-i-made-the-bbc-hall-of-fame-3-times-2c816fa515d7
- https://infosecwriteups.com/sql-injection-at-spotify-d19e0861ddf0

#### Learned:

1. The Website Using same Hosting/server to store different people's files. Attacker Just Replace the Username and he got many sensitive files (https://iamxkurtph.ml/shell.php?path=/home/vol11_6/epizy.com/epiz_30774583/htdocs/images) change epiz_30774583 to epiz_30774584. epiz_30774585 etc.	
2.
      - Javascript gives a email to testing
      - Insecure API gives PII data leakage.
      - Found Endpoint Using JS recon
      - I found an endpoint that when browsing straight from the homepage to the endpoint, we were met with 500 Internal error. But, if I started the 2FA flow, my non authenticated account was assigned cookies, this then bypassed the 500 Internal error and the application assumed I was authenticated against the email address to query the endpoint, leaking the phone number associated to the account, this is evidently PII leak.
      - After 6 login attempt,  The account was locked, the password reset and a user had to then visit their email to reset the password, By doing this we can terminate a valid loged in user session.

3. Simple Methodology To Find SQL Injection.

  - Try to inject some malicious characters like ' \ / to check if the response changed, or you gained a SQL error.
    At the backend, if you inject ' after the entered number. Select random_data From random_table where user_input='122'' and aykalam='1'; So it will generate an error or the response will be different. And if you managed to detect an error, try to balance the query by using the balancing characters like ' ') " ") ')) "))
  - Try to use order by and union queries if you didn’t gain error or change in the response.
  - Try to use blind commands like sleep command and check the response time and response behavior
  - Found a Vulnerable endpoint and balance it using (calculator_input=122 and 100=100-- - "Successed") and we have SQL Injection.
  
### 2. TryHackMe Labs:

- [X] Solved Task 6, Task 7 And Completed The Room Of **METASPLOIT** : https://tryhackme.com/room/rpmetasploit 
- [X] Solved Task 3 And Completed The Room Of : **Dirty Pipe** : https://tryhackme.com/room/dirtypipe  (This Time Got the ROOT Flag)

### 3. PortSwigger Labs:

- [X] **Solved Directory traversal**
 -  Lab: File path traversal, traversal sequences stripped non-recursively
 -  Lab: File path traversal, traversal sequences stripped with superfluous URL-decode
 
 ### 4. Youtube Video:

- Watched : OrwaGodFather Part 2 Video : https://www.youtube.com/watch?v=YoXM4m1VEM0&t=1s

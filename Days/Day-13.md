# Day-13 (30-Days-Of-Hacking)

### 1. Read 3 Article: [DONE]

- https://f4t7.medium.com/xss-in-hidden-input-field-1b98a5fece26
- https://f4t7.medium.com/interesting-stored-xss-d741aabddb94
- https://f4t7.medium.com/an-interesting-reflected-xss-5456a00dc8be

#### Learned:

1. From Article 1:
      - Before we dive in. let’s discuss how an input field is hidden from the web page. There are various ways to hide an input field, from which the two are: `Using type=”hidden” attribute inside an <input> tag`, `Putting the <input> tag inside another element and setting its style to display:none`.
      - In my case the <input> tag was inside the <div> element like: `<div style=”display:none”><input type=”text” value=”somevalue”></div>`.
      - After playing around multiple attributes, I came across an attribute called pattern. This attribute is used to compare value and pattern it is same as an if condition, if pattern matches and is valid do something else if invalid do something else. After providing the payload the response looked like this.
	- `<div style=”display:none”><input type=”text” value=”somevalue” pattern=”somethingelse” oninvalid=”alert(document.cookie)”></div>`. I sent the request again and opened the browser, the pop up appeared on the screen!.

2. From Article 2:
    - I was playing around with its requests in Burp suite and I noticed something strange in `redacted.com/somedirectory/file.html`.
    - While looking for input fields I saw a script tag which looked something like, `<script type=”text/javascript” src=”https://another_redacted.com/some_directory/some_child_directory/file.js”></script>`.
	- I opened this URL from the src attribute in new tab and what happened was unexpected!. It threw an error! “Page does not exist!”.
    - I quickly went to `https://www.namecheap.com/domains/registration/results/?domain=another_redacted.com`. Where I found that the domain was available for sell.
	 - Well if not! I can purchase this domain and create the same directory in the domain, make a file.js and write my own payload i.e. `alert(document.cookie)` .As simple as that.

3. From Article 3:
    - Lets suppose the website is https://redacted.com. I logged into the web application and the first page had a parameter ‘1’ like, `https://redacted.com/…/pg/1`.
    - I captured the request in burp suite, sent it to repeater and changed the parameter to 123 to check whether it was reflecting or not, The parameter was reflecting in a function under java script tag.
    - Then I shared it with my cousin. He simply replaced the page number i.e 123 with `alert(1)`, It got triggered an alert right away.

### 2. TryHackMe Labs: [DONE]

 - [X] Solved Complete Room On **Wifi Hacking 101** : https://tryhackme.com/room/wifihacking101

### 3. PortSwigger Labs: [DONE]

 - [X] **Information disclosure (4/5)**
 -  Lab: Authentication bypass via information disclosure    (https://portswigger.net/web-security/information-disclosure/exploiting/lab-infoleak-authentication-bypass)

### 4. Youtube Video: [TODAY TIRED AF HAVEN'T WATCHED ANYTHING]

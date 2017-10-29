# Project 8 - Pentesting Live Targets

Time spent: 2 hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection
	Details: The saleperson information for blue site does not santatize the data. In the detail infomation of salepersons, if we add ' OR SLEEP(5)=0--' in the url after ?id=, it causes the page to take 5 second to load and change back to the first saleperson Daron Bruke
	
	Walkthrough: 
  <img src='https://i.imgur.com/qL7tywc.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />

Vulnerability #2: Session Hijacking/Fixation
	Details: The session for this website is not expired. When an admin log in from a browser, the session id remains the same. The attacker can stole that session id and log in without knowning username and password.
  
  Walkthrough:
  <img src='https://i.imgur.com/EmYRrzT.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />


## Green

Vulnerability #1: User Enumeration
	Details: When enter a valid username and random password, the error message is bold and the class is "failure". When the enter a non-exist user, the error message is not bold and the class is "failed". The exploit can be used by attacker to find a valid user.
  
  Walkthrough:
  <img src='https://i.imgur.com/Xk7nZIP.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />

Vulnerability #2: Cross-Site Scripting
	Detail: The comments section in this side is vulnerable to a stored XSS attach. The attacker can leave a comment with inject a script (ex: <script>alert('Mallory found the XSS!');</script> ), when the admin opens feedback section, the script got executed.
  
  Walkthrough:
  <img src='https://i.imgur.com/HOCnzAK.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />



## Red

Vulnerability #1: Insecure Direct Object Reference
	Details: The salepersons can be access through id. all the visible salepersons have id from 1 to 9. On the red website, you can access invisiable salepersons with id = 10 and id = 11. You can not do that on green and blue sites. The developer didn't disbale those id and accidentally created IDOR vulnerability.
  
  Walkthrough:
  <img src='https://i.imgur.com/39pbxLy.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />

Vulnerability #2: Cross-Site Request Forgery
	Details: A link with malicious form is posted in comments section, when admin see the comment a click the link, will use admin's session to forge a request to the database. In the example, it creates a new saleperson without admin knowledge. 
  
  Walkthrough:
  <img src='https://i.imgur.com/HvgSLrb.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />

## Notes

This assignment is fun. I learn a lot.


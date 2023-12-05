# OWASP Top 10 – 2021

## Broken Access Control
```Broken access control allows attackers to bypass authorization, allowing them to view sensitive data or perform tasks they aren’t supposed to.
In this room we learn that the url of a bank displays the ID of the customer plaintext, if we were to change to another id lets say, we could easily see and/or use the data of another customer. This is called Insecure Direct Object Reference or IDOR which refers to an access control vulnerability where you can access resources you wouldn't ordinarily be able to see.
```
## Cryptographic failures
```
A cryptographic failure refers to any vulnerability arising from the misuse (or lack of use) of cryptographic algorithms for protecting sensitive information. Web applications require cryptography to provide confidentiality for their users at many levels. In this challenge we get to explore a web app for potential failures. We can see that the developer accidentally left something in the source code of the login.php file, where it says that an endpoint or directory contains sensitive data which is /assets and from there on out we can eventually log in as admin.


The most difficult part of this challenge was to find in which file the developer had left the clue.
```

## Injection
```
Injection flaws are very common in applications today. These flaws occur because the application interprets user-controlled input as commands or parameters. Injection attacks depend on what technologies are used and how these technologies interpret the input. 

Our challenge was reverse shell injection, for example we needed to find files in the websites root directory and find info about the user aswell. 
```
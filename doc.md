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

## Insecure Design
```
Insecure design refers to vulnerabilities which are inherent to the application's architecture. They are not vulnerabilities regarding bad implementations or configurations, but the idea behind the whole application (or a part of it) is flawed from the start.

In this challenge we get the example of instagram and their insecure design with the rate limiting on passwords reset.

And we can try something similar aswell, where we can exploit the forgot my password feature of a user named Joseph where we get 3 options to choose from, the hint of the question was to choose the option which is the easiest to guess which was the 'colour' one. From there on out we can go to the 'private' tab and see the flag.
```

## Security Misconfiguration
```
Security Misconfigurations are distinct from the other Top 10 vulnerabilities because they occur when security could have been appropriately configured but was not. Even if you download the latest up-to-date software, poor configurations could make your installation vulnerable.
```
Security misconfigurations include:

- Poorly configured permissions on cloud services, like S3 buckets.
- Having unnecessary features enabled, like services, pages, accounts or privileges.
- Default accounts with unchanged passwords.
- Error messages that are overly detailed and allow attackers to find out more about the system.
- Not using HTTP security headers.

```
One example of such a vulnerability was allegedly used when Patreon got hacked in 2015. Five days before Patreon was hacked, a security researcher reported to Patreon that he had found an open debug interface for a Werkzeug console. Werkzeug is a vital component in Python-based web applications as it provides an interface for web servers to execute the Python code. Werkzeug includes a debug console that can be accessed either via URL on /console, or it will also be presented to the user if an exception is raised by the application. In both cases, the console provides a Python console that will run any code you send to it. For an attacker, this means he can execute commands arbitrarily.
```

```
So for this room we entered the console of the given website of the challenge and we got to play around for a little bit with the python commands.
```

## Vulnerable and outdated components
```
Occasionally, you may find that the company/entity you're pen-testing is using a program with a well-known vulnerability.

For example, let's say that a company hasn't updated their version of WordPress for a few years, and using a tool such as WPScan, you find that it's version 4.6. Some quick research will reveal that WordPress 4.6 is vulnerable to an unauthenticated remote code execution(RCE) exploit, and even better, you can find an exploit already made on Exploit-DB.
```

```
In this challenge we exploited an outdated CSE Bookstore version, we used exploit-DB to try and find an exploit for this particular version. And after running the script we have access to information that shouldn't be public. For us that means we found the flag.
```

## Identification and Authentication Failures
```
Authentication and session management constitute core components of modern web applications. Authentication allows users to gain access to web applications by verifying their identities. The most common form of authentication is using a username and password mechanism. A user would enter these credentials, and the server would verify them. The server would then provide the users' browser with a session cookie if they are correct. A session cookie is needed because web servers use HTTP(S) to communicate, which is stateless. Attaching session cookies means the server will know who is sending what data. The server can then keep track of users' actions. 
```

```
So for this room we tried to register as "darren" but this user already exists, but if we were to register as " darren" (so with a space before the name) it would allow us to register and also with the same rights and privileges as "darren" only now with our email and password and this led us to the flag.
```
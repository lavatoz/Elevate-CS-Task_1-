1. Understanding OWASP Top 10
Before hacking, I studied the OWASP Top 10, which is the industry-standard list of the biggest web security risks.

2. Lab Setup
I set up two "punching bag" applications to practice on:

DVWA (Damn Vulnerable Web App): A classic PHP app for practicing SQLi and XSS.

OWASP Juice Shop: A modern Javascript app for practicing modern web flaws.

3. Intercepting Requests (Burp Suite)
I used Burp Suite as a "Man-in-the-Middle" proxy. It allowed me to catch a request from my browser, change the data (like a price or a username), and then send it to the server.

4. Testing SQL Injection (SQLi)
The Hack: I entered ' OR 1=1 # into the login box.

The Result: The database was tricked into thinking the password was correct for every user. I successfully logged in as the Admin without a password.

5. Testing Cross-Site Scripting (XSS)
The Hack: I typed <script>alert('Hacked')</script> into a comment box.

The Result: The website "stored" this script. Now, whenever anyone visits that page, a popup appears on their screen, proving I could steal their session cookies.

6. Observing Application Responses
I didn't just look for "Success" or "Failure." I watched Burp Suite for:

HTTP 500 Errors: Hinted that my SQL code broke the database.

Response Length: Different sizes in the data helped me find hidden admin pages.

7. Documenting Vulnerabilities
I recorded every bug with:

Severity: How dangerous is it? (Critical, High, etc.)

PoC (Proof of Concept): The exact steps and screenshots to prove the bug exists.

8. Suggesting Mitigations (The "Fix")

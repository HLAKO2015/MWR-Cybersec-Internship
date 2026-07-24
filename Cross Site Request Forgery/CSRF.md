# 7. Cross Site Request Forgery (CSRF)
## A
- Vulnerability in the design of browser and request
- Root Cause : Application having a fully definable HTTP request
- Affecting only applications using cookie-based authentication
- Request must be state changing

## B
- Forces the victim to make HTTP request on the attacker's behalf
- The request is made with the context of the current user
- It will include a session cookie
- Since browsers automatically attach cookies to requests

![alt](https://github.com/HLAKO2015/Images/blob/main/MWR%20CyberSec/Week%207/Screenshot%202026-04-14%20184856.png)

## 7.1 How to think of it
- Victim logs into a bank account
- Bank assigns a token to the victim
- Attacker send a link, via any mode of communication (Email, SMS, WhatsApp,...) of a forged request to the victim
- Victim unknowingly issues forged request to bank (By clicking the link or just opening message, this depends on how the attacker crafted their script/request)
- Forged request is then executed by the victim using session token

## 7.2 Remembering SOP and CORS
### 7.2.1 Cross-Origin
- Writes : Links, redirects and form submission are permitted by default
- Embedding : Scripts, stylesheets, images, media files, objects, and applets are also permitted by default
- Reads : Provided by the XHR and Fetch APIs are not permitted

### 7.2.2 SOP breaks our design
- bank.com can't access what admin.bank.com capabilities can d

### 7.2.3 CORS
- Cross Origin Resource Sharing
- Relaxes the SOP
- Used by servers to define what content they are to share and to who

### 7.2.4 Since SOP breaks our design, we are going to use CORS to fix it
- Now bank.com can access what admin.bank.com capabilities can do

## 7.3 Key points
- In CSRF a GET request is easy, just hide the in a page
- POST : Create your own page with a form or XHR payload
- To be successful in CSRF, you need :
  1. Remove as much info that may be suspicious to the user as possible
  2. Craft a working script, because requests rely on cookies for authentication
  3. Series of chain of attacks (CSRF File Upload -> Redirect to the uploaded HTML file -> XSS)

### 7.3.1 Synchronize Token Pattern 
- AKA CSRF token
- Include random token associated with the user's current session with the HTML forms/links associated with sensitive server-side operations
- Check the validity of the token server-side when the operations is performed

### 7.3.2 Cookie Security Flag
- You can leverage the "SameSite" flag on your cookies to prevent a Cross Site Request (XSS) from forwading the users' credentials
- The flag however is not currently supported in all browsers, so you should be used along CSRF token

## Practical Demo 
-





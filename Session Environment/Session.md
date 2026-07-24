# 3. Session Environment (Authentication, Login, and Cookies)

## 3.1 Authentication
- Consits of IAAA (Identification, Authentication, Authorisation and Accountability (Auditing))
- Determines whether or not a person claims they are who they are

### Lacks of Authentication
- No sessionID : Means no trusted request and/or user is not authenticated
- Access all info without being authenticated

### Cookie security flags
- HTTPonly : Prevents JavaScript from accessing a cookie, helping protect it from Cross-Site Scripting (XSS) attacks
- Secure : Ensures that a cookie is only transmitted over encrypted HTTPS connections, reducing the risk of interception
- SameSite : Controls when a browser sends cookies with cross-site requests, helping protect against Cross-Site Request Forgery (CSRF) attacks

### How does Web Application know who you are

#### Session vs Token Authentication
|Session | Tokens|
|--------|-------|
| Server issues cookie with sessionID | Web uses Json Web Tokens (JWTs) and Rest APIs|
| Session value is transmitted in the cookie's request header to the server | Server creates JWT with secrets & sends JWT stored locally to client. Client includes the JWT in every request|

### HTTP cookies
- Are name-value pairs used to track user state through app usage
- Server sets cookie using "Set cookie" in the HTTP response header
- Client sends cookie with each subsequent request using the cookie
- Sent with request to its associated domain and path
- No domain, browser automatically locks it down to only the issuing domain

## Thinking like an attcker and a defender at the same time

### Usename Enumeration
- Enumerate (Figure out) valid username of the target user
- Ways to to this :
- Public profiles
- Differing error messages on the Login page
- Forgoten password functionality
- User registration functionlity

### Login Features & Password reset features
- Username exists/found
- Bad credentials
- User not found
- User found and email sent

### Password Attacks
- Users ussually set weak password that can be guessed
- A password should be hard to guess but easy to remember
- Password guessing can be automated these days
- Passwords can brute forced known wordlists like the famous "rockyou.txt"

### Lack of Account lockout
- Developers forget to impelment the lockout feature when multiple login attempts fail
- This can lead/ facilitate enumeration or brute force attacks

### Password spraying
- Similar to brute force but focuses on iterating usernames instead of passwords
- Given/Known password said to be valid , iterate all the usernames in an attempt to find a matching username with the password

## Practical Demo
- Hydra tool (Password guessing tool)
  e.g hydra -l "admin" IP_Address http-post-form n "/login.username_field=^USER^ Pass_field=^PASS^ :uknown user" -V
- Using Nmap
  e.g nmap 123.90.98.3
- Gobuster (Director enumeration)
  gobuster dir -u 123.90.98.3/URL/http://123.90.98.3/ -w wordlist -dir
  
 


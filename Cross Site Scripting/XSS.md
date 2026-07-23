# 5. Cros Site Scripting (XSS)
## 5.1 SOP and CORS

## SOP (Single Origin Policy)
- Prevents cross-origin issues
- Prevents hacker.com from accessing bank.com
- An origin is a Scheme, domain, or port

## CORS (Cross-Origin Resource Policy)
- Is a set of HTTP headers designed to relax the SOP
- Used by servers to define what content they are happy share and to who

## Cross Site Scripting
- Can insert arbitrary code in the application to manipulate the site
- We can execute on the hosts computer
- Uses the hosts machine's resources

### Types of XSS
- Reflected : Malicious payload sent to the server is returned within the response
- Stored : Stored within the application and returned to any user accessing affected content
- DOM (Document Object Model)

## Defense
- Encode first, then validate input

## Practical Demo
- 

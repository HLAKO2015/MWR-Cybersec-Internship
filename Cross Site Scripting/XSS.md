# 5. Cros Site Scripting (XSS)
## 5.1 SOP and CORS

### 5.1.1 SOP (Single Origin Policy)
- Prevents cross-origin issues
- Prevents hacker.com from accessing bank.com
- An origin is a Scheme, domain, or port

![alt](https://github.com/HLAKO2015/Images/blob/main/MWR%20CyberSec/Week%205/Screenshot%202026-03-31%20182734.png)

### 5.1.2 CORS (Cross-Origin Resource Sharing)
- Is a set of HTTP headers designed to relax the SOP
- Used by servers to define what content they are happy share and to who

### 5.1.3 Cross Site Scripting
- Can insert arbitrary code in the application to manipulate the site
- We can execute on the hosts computer
- Uses the hosts machine's resources

### 5.1.4 Types of XSS
- Reflected : Malicious payload sent to the server is returned within the response
- Stored : Stored within the application and returned to any user accessing affected content
- DOM (Document Object Model)

### 5.1.5 Defense
- Encode first, then validate input

## Practical Demo
- 

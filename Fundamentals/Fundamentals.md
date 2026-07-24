# 1. Web Fundamentals
## 1.1 Protocols
HTTP - HyperText Transfer Protocol ( Exchange resources such HTML documents between the client and server);
### 1.1.1 How this works
- A client opens a TCP connection to a server (to make a 3 way handshake)
- Client send a human readable message to the server this is known as a request
- Server processes the request and responds with the required data
- Client terminates or re-uses the connection for further request


### 1.1.2 Popular HTTP Response status
- 100 continue
- 200 OK
- 201 Created
- 301 Permanently moved
- 401 Not modified
- 403 Forbidden
- 404 Not found
- 500 Internal server error
  

### 1.1.3 HTTP Requests and Responses
- Consits of methods (POST, GET,...), path
- Protocol version
- Header name
- Headers
- Status code
- Status message

![alt](https://github.com/HLAKO2015/Images/blob/main/MWR%20CyberSec/Week%201/Screenshot%202026-03-03%20184154.png)

### 1.1.4 Web Proxies
- Sit in between the client and the server, most requests and responses pass through them

## Practical Demo
- Introduction to Burp Suite Community Edition
- Set the Target scope, so that other web pages may not be interrupted
- Turn on "Proxy", turn on the "Interceptor" to stop the request and be able to modify them
- Intruder : Allows spraying the endpoints with requests
- Repeater : Allows capturing, modifying, and resending the same request multiple times
- Also install Foxy-Proxy to set a Proxy on the Web browser

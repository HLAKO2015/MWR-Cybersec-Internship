# 10. Injection Attacks
- Attacker send malicious input to an application, causing it to execute unintended commands or reveal information that it shouldn't

### (i) How injection attacks work
- User submits input
- Application fails to validate input or sanitize it
- Input is passed directly into an interpreter (Database, operating system or scripting engine)
- The interpreter executes the commands

### (ii) Common types of these attacks
- SQL Injection
- XPath Injection
- XML Injection
- NoSQL Injection

## 10.1 XPath Injection
- Parametirized XPath Interface
- Escape user input if neccessary to insert it into dynamically created XPath queries
- Precompile XPath queries

## 10.2 OS Command Injection
- Similar to SQL Injection, ocassionally functionality exists which allows for the injection of operating system commands



# 6. XSS and DOM
- In cybersecurity 1 vulnerablility = 1 Remediation
- DOM : Programming interface for web documents, represents the page so that programs can change the document structure, style content, represents document as nodes and objects. Programming languages interact with the page

## 6.1 How do I know its DOM-based
- Payload doesn't get sent to the server
- If it does check where it executes :
- HTML = Normal
- But where in HTMl and how
- In the DOM ?

## 6.2 Some terminologies
- Source: Raw HTML code, while the DOM is dynamic, in-memory representing of that web page created by the browser for dynamic updates
- Sink : JavaScript function, DOM object causing undesirable effects if attakcer-controlled data is passed to it

### 6.2.1 Source and Sink
| Source | Sink |
|--------|------|
| document| document.write()|
| history | window.location |
| IndexedDB | eval() |
| Database | ExecuteSQL() |
| Local Storage | webSocket() |
| Session storage | RegExp() |
| window.name | |

### 6.2.2 Root Cause
- Ingesting unencoded user input as part of a web page

### 6.2.3 Remedical Action
- Encode the user input
- Implement input validation
- Remove dangerous JavaScript function

### 6.2.4 Reconnaissance (Knowing things about a system)
- Passive : Attempt to gain infomation about a target system without engaging with the system
- Active : Gaining information by actively engaging with the target system

### 6.2.5 Vulnerablity Identification
- Test application, use your knowledge from reconnaissance and try to find any issues in within the application

### 6.2.6 Exploitation
- Take all vulnerabilities found, combine them to acheive some goal

### 6.2.7 Documentation and Reporting
- The only important outcome of a pentest is the report
- The quality matters
- If it's not in the report, then it didn't happen

## Practical Demo
-



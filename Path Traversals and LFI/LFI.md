# 11. Path Traversals and Local File Inclusion (LFI)

## 11.1 Path Traversals 
- Every application has a  web root folder on hard disk corresponding to the URL namespace of the website
- Web root is the publicly-accessible base folder for the website
- Consists of all the files required to be used in the website
- E.g www.mywebsite.com with index.html -> www.mywebsite.com/index.html
- We can sometimes upload media to the web root

### 11.1.1 What could we access through Path Traversals
- Source code, certifications, configuration files
- On Linux vs Windows

| Linux | Windows |
|-------|---------|
|application.properties | Web config |
|htaccess | C/Windows/win.ini |
|/etc/shadow | C/MySQL/my.ini |
| ect/passwd | C/apache/logs/access.log |

### 11.1.2 More on Path Traversals
- Store sensitive information outside the root web
- Directory Traversal : Method for accessing files and directories that are outside of the web root directory or any other directory
- Achieved using absolute path
- Eg /root/to/file/../../other/file
- Path Traversal in not LFI or RFI

### 11.1.3 Path Traversals
- Direct traversal : example.lab/download?file=../../../../../../etc/passwd
- Prefix validation : example.lab/download?file=trusted/../../../../../etc/passwd
- URL encoded : example.lab/download?file=..%2F..%2F..%2F..%2F..%2F..%2Fetc/passwd
- Double URL encoded : example.lab/download?file=..%252F..%252F..%252F..%252F..%252F..%252Fetc/passwd

### 11.1.4 Files Includes
- Processed server-side to build the contents of the page, before the page is returned to the user. As such, only nested server-side code will be executed
- Takes all the content that exists within a specified file and copies it into that uses include statement

### 11.1.5 XML external entities
- Disable Document Type definitions (DTDs) or external entities completely
- Configure XML processor to use a local, static DTD and do not allow DTDs to be declared via user input
- Could also perform input validation, but this is not really considered a robust control XEE attacks

## 11.2 Local File Inclusion
- Only read files
- Must be able to read file outside the web root
- Can lead to Remote Code Execution (RCE)
- LFI is a php thing, if not php then it's not LFI

## 11.3 Extra Mitigations
- Each NoSQL DBMS will have its own solution to some of these problems, for example, MongoDB allows you to stop server-side scripting to help mitigate NoSQL inject
- This is unique to each database and requires research

## Practical Demo



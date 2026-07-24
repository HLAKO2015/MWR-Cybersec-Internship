# 9. File Upload
- When a web server allows you to upload files to its file system without validating the name, type, contents and size
- Failling to put restrictions to this can be dangerous
- Include server-side script files that enable remote code execution

## 9.1. What are the impacts of this vulnerability
- Depends :
  1. Which aspect of file, a website fails to validate (size, type or contents)
  2. What restrisctions ar imposed on the file once it has been successfully uploaded
 
## 9.2 How do File Upload vulnerabilities arise?
- Developers believe to have implemented robust validation that is either flawed or can be easily bypassed
- Website may attempt to check the file type by verifying the properties, which can be aminpulated easily by an attacker using tools like Burp Suite

## 9.3 How do web servers handle requests for static files
- In the past websites consisted of static files provided to user when requested, but now we redirect
- But still some websites deal with requests for some static files, stylesheets and images
- Servers parse the path in the request to identify the extention
- Uses this to determine type of file requested by comparing it to a list of preconfigured mappings between extentions and MIME
- What happens next depends on the file type and server's configurations

  ### (a) Non executable file types (Images, Static HTML page)
  - The server just bends the contents to the client in an HTTP response

  ### (b) Executable (php Files)
  - Server is configured to execute this file types, it will assign variables based on the header and parameters in the request before ruuning the script. The output may be sent to the client in response

  ### (c) Executable but not configured by server
  - Generraly response with error, sometimes contents may be still be served to the client as plain text
 
## 9.4 Exploiting unrestricted file upload to deploy a web shell

### 9.4.1 What is a Shell
- Remote code execution
- Can be a backdoor to a server, web shell, payload, command and control, remote access trojan
- Executing this type of malware is "HARD" indeed

### 9.4.2 Worst case scenario
- Website allow you to upload a server-side script (php, java, python files) and configured by server to execute them as code


## Practical Demo
  

# 4. Authentications and Authorisation

## 4.1 Tokens vs Sessions

### JWTs
- Self-contained way of securely sending data between parties using JSON objects
- It has a header, payload and signature
  header.payload,signature
- Use a Decode from Burp Suite to decode the payload

### JWTs security considerations
- Signature is not verified at all (This can allow attakcer to edit the JWTs)
- Token information disclosure
- No sensitive information should be stored in JWTs
- Attacks can simply decode the token and gain access to the information

### Authorisation
- After determining what the person can do
- We know who you are, you are now bound by what you can do

### Priviledge Escalation
- User gaining access to resources beyond their priviledges via broken authorisations
- Vertical : Access resources granted to more priviledged accounts
- Horizontal : Access resources to a similar confirmed account
- User can go to different accounts/endpoints by changing the values on the querystring.

### Client-Side Authorisation
- Authorisation controls should be replicated server-side
- Restricting access via the UI only is bad
- This could allow attacks to access endpoints directly

## Practical Demo
- Authorisation & Authentication attacks vectors
- Bypassing Authentication and Authorisation
- Cracking JWTs secrets using "hashcat"

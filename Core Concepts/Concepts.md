# 2. Core Concepts {Encoding, Encryption and Hashing}

## 2.1 Encoding 
- Taking data from one format to another format
- We have URL encoding, Base64, and HTML encoding

## 2.2 Encryption
- Used for confidentiality and integrity
- The data received on the internet should exactly be the same one as it was send (No packect loss)
- Backbone for security on the Internet
- Encrypted keys need keys to decrypt
- CIA triad (Confidentiality, Integrity and Authenticity)

### 2.2.1 Two types of encryption 
- Symmetric Encryption : Same key for encryption and decryption
- Assymetric Encryption : Different keys, each party has public-private key pairs

## 2.3 Hashing
-  Store data you need to validate
-  Can't get original data from hash (Data can be lost during hashing)
-  One way algosithm that can't be reversed

### 2.3.1 Hashing for passwords
- Confidentiality
- Prevents the storage of actual real passwords
- Ensures integrity of data

### 2.3.2 Hash Collisions
- Inputs map to the same data
- Problem : Attacker can find a pair of messages that collide, and then find a collision given a message

### 2.3.3 Hashing types
- MD5
- SHA
- SHA-5

### 2.3.4 How to crack a password hash
- Find the type of hash first (use "hashid")
- Generate hashes from well known lists (eg /user/share/wordlist)
- Generate a hash for each password,  in the input
- If they match, we found the original password

## Practical Demo
- Using the following commands:
- echo (for output)
- ls (for listing)
- nano or vim (for a textfile)
- cat (for concatenating files) 

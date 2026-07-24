# 8. SQL Injection
- Attacker injects malicious SQL code in the input fields to manipulate the Database into giving information
- Targets applications using SQL to talk to their database
- Bypasses authentication

### (i) How it works
- Trusting user inputs
- Attaker changes conditions to always be true (' OR 1=1 --)
- Skips password checks
- Alters how the query is interpreted
- Database returns data it shouldn't

### (ii) Root cause
- User input is treated as part of the SQL code instead of data

### (iii) Remedial actions
- Make sure that user input never changes the structure of the SQL query (Use prepraredStatements)
- Use prepared query/statements
- Parameterise queries
- Use ORM frameworks
- Least priviledges
- Error handling

### (iv) Why validatinf user input isn't remedial action
- Validation can bypassed
- You are just treating the symptom, not the disease
- Doesn't fix the root cause

## 8.1 In-band vs Out-of-band Injection

### 8.1.1 In-Band
- Can see results directly in the application's graphicAL user interface
- Same channel in, same channel out
- Attacker :
  1. Sends injection through and application
  2. Gets response via the same application UI in the HTTP response
- How it works :
  1. Attacker performs SQL Injection
  2. Results displayed in the web page or error message
- Types : Error-based and Union-based


### 8.1.2 Out-of-band
- Indirect feedback through external systems
- Different channel for the response
- Attacker :
  1. Injection via the application
  2. But data comes back through a separate channel
- How it works :
  1. Instead of showing results on the page, the database might
  2. Send DNS request
  3. Make HTTP call to attacker's server
  4. Attacker captures the data here
- When is Out-of-band used :
  1. When app doesn't return query results
  2. When error message is hidden
  3. When in-band method fails

- The attacker doesn't rely on app's response to get data

## 8.2 Inference attacks
- Don't get output "force errors" or "force delay"
- Dump DB with only asking true or false questions

## 8.3 SQL injection Defense
- Parameterise queries
- Don't concantenate user input directly with SQL query

## 8.4 Key points
- Does input look like it feeds into a query? or it interacts with the database? Try to inject into it
- Focus on trying to break the syntax and throw and error to begin with
- Then try to create a basic boolean statememt
- Then try a UNION statement to get more information from the database

## Practical Demo

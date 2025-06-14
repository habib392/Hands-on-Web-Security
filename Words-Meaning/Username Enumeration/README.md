# Username Enumeration

Hum computer se poochte hain sahi username kaunsa hai. Agar 3 usernames try karein, 
aur 2 pe same response aaye aur 1 pe alag, to wo 1 valid username hai.

### Username Enumeration
Server ki response messages ya behavior
(status code, response time, message length) ko observe karke valid username pakadna.

### 💡 Real-life Example:
POST /login HTTP/1.1

username=ali&password=test

agar username ghalat hai to message aaye:
❌ "Invalid username or password"

agar username sahi hai lekin password ghalat ho to:
⚠️ "Too many login attempts"

⛳ Toh attacker samajh gaya: ali = valid username

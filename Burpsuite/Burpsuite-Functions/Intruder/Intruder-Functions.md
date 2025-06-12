# Four Types of Attack Options

### Sniper Attack –

Tum sirf ek field (jaise username ya password) ko test kar rahe ho
Baqi fields same rehti hain

**Example:**
Tumne target kiya sirf username field
List di: admin, user1, guest
Password fix rakha: 123456

🔫 Burp try karega:

admin : 123456  
user1 : 123456  
guest : 123456

🟢 Sahi usage: Jab sirf ek parameter test karna ho.

### Battering Ram – “Ek hi payload sab fields mein”

✔️ Ek hi value har jagah pe try hoti hai
✔️ Dono fields mein same value jaati hai

**Example:**
Payloads: admin, test123, guest123

🔫 Burp try karega:
Username: admin | Password: admin  
Username: test123 | Password: test123  
Username: guest123 | Password: guest123

🟢 Sahi usage: Jab username = password type cases check karne ho.

### Pitchfork – “Har banda apni line ka combo try kare”

> ✔️ Username aur password alag alag list se lekin line by line match hote hain

**Example:**
Usernames: admin, user, guest
Passwords: 123, pass, admin123

🔫 Burp try karega:

admin : 123  
user  : pass  
guest : admin123

🟢 Sahi usage: Jab har username ke liye ek matching password test karna ho (line by line).

✅ Cluster Bomb – “Har combination try karo”

> ✔️ Username aur password ke sab combinations test karta hai

**Example:**
Usernames: admin, user
Passwords: 123, pass

🔫 Burp try karega:

admin : 123  
admin : pass  
user  : 123  
user  : pass

🟢 Sahi usage: Jab tum har username ke saath har password test karna chahte ho (brute force style).


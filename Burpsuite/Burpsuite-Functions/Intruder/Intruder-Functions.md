# 🔐 Four Types of Attack Options in Burp Suite Intruder

## 🎯 1. Sniper Attack

Sniper attack tests only **one input field** at a time (like username or password).  
All other fields stay the same.

**Example:**
- Target field: username
- Payload list: `admin`, `user1`, `guest`
- Password: fixed → `123456`

👉 Burp will send:

admin  : 123456
user1  : 123456
guest  : 123456

✅ **Use When:** You want to test only one parameter.

## 💥 2. Battering Ram

This attack uses the **same value** in **all input fields**.

**Example:**
- Payloads: `admin`, `test123`, `guest123`

👉 Burp will send:

Username: admin    | Password: admin
Username: test123  | Password: test123
Username: guest123 | Password: guest123

✅ **Use When:** Username and password are the same (like `admin:admin`).

## 🔁 3. Pitchfork

This attack uses **two different lists** — one for each field — and matches them **line by line**.

**Example:**
- Usernames: `admin`, `user`, `guest`
- Passwords: `123`, `pass`, `admin123`

👉 Burp will send:

admin : 123
user  : pass
guest : admin123

✅ **Use When:** You want to test each username with its own password (same line).


## 💣 4. Cluster Bomb

This attack tries **every possible combination** of usernames and passwords.

**Example:**
- Usernames: `admin`, `user`
- Passwords: `123`, `pass`

👉 Burp will send:

admin : 123
admin : pass
user  : 123
user  : pass

✅ **Use When:** You want to test **all combinations** (brute force style).
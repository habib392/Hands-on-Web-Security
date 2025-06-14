# What Are Parameters?

Web parameters wo data hote hain jo user browser se server ko bhejta hai — taake server uss data ke basis pe kaam kare.

Login form mein username aur password parameters hote hain. Yeh mostly URL mein ya form ke andar hote hain. Attacker inhi parameters ko modify karke injection, bypass, ya data access karta hai. Parameters GET aur POST dono mein hote hain. Har web app parameters pe depend karti hai — agar secure na ho to hacker exploit kar leta hai.

Parameters mostly 4 jagah hotay hain:

🔹 URL (GET request)

🔹 Form Body (POST request)

🔹 Cookies

🔹 Headers

🎯 Golden Rule:

✅ Jis element ke sath name="..." ho ya URL mein = ho, wo parameter hai.

### 🛠️ Example 1: URL-based Parameters (GET)

**https://example.com/product?item=chair&color=red&price=500**

Parameters:

item = chair

color = red

price = 500


### 🛠️ Example 2: Form-based Parameters (POST)

<form action="/login" method="POST">
  <input name="username" type="text">
  <input name="password" type="password">
</form>

Parameters:

username

password

### 🛠️ Example 3: Hidden Parameter (Used for CSRF, Tracking)

<input type="hidden" name="csrf_token" value="abc123">

Parameter: csrf_token

**Input type, ya phir value kabhi parameters nhi hoo skty**

URL mein parameters dhoondhna asaan hota hai jo bhi = ke sath ho, wo parameter hota hai.

Lekin website ke andar (jaise login form, contact form, ya hidden fields) mein parameters thode chupay hote hain — lekin unko dhoondhna bhi asaan hai.

### Important Key Points:

1. type="..." ya value="..." = Parameter nahi hote

2. name="..." = Yahi parameter ka naam hota hai

3. URL mein = ke pehle wali cheez = parameter name

4. Parameter har form ka part hota hai, even agar wo hidden ho

5. Burp Suite se request dekh ke asaani se parameter samjhe ja sakte hain

6. Attackers form manipulation ya URL tampering se unauthorized access lete hain

7. Parameter manipulation se bug bounty milta hai (IDOR, XSS, etc.)

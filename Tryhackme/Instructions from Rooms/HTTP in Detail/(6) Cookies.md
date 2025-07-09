## 🔹 Cookies kya hoti hain?

Cookies ek **chhota sa data hota hai** jo tumhare browser (yaani tumhare computer) pe **server save karta hai**.
Jab bhi server tumhein ek `Set-Cookie` header bhejta hai, browser usay **save kar leta hai**.
Aur phir jab tum agla request bhejtay ho, toh browser **wohi cookie wapas server ko bhejta hai**.

---

### ⚠️ Kyun zaroori hain cookies?

Kyunke **HTTP stateless** hota hai — yani server ko yaad nahi rehta ke tum kaun ho ya kya kiya tha pehle.
Toh **cookies use hoti hain user ko pehchanne ke liye.**

---

### 🔸 Example uses:

* **Login session**: Tum login karte ho, toh server tumhein ek token deta hai cookie ke through,
  jisse woh tumhein pehchanta hai: “Yeh Habib hai, yeh login ho chuka hai.”
* **Website settings**: Jaise dark mode, language preference.
* **Tracking**: Kuch websites tumhein track bhi karti hain ads ke liye — privacy point of view se yeh critical hota hai.

---

### 🧠 Cookie ka format clear-text nahi hota

Matlab, cookie ke andar **password ya sensitive info plain text mein nahi hoti**.
Uski jagah ek **token ya session ID** hota hai — ek unique, random sa code jisse server tumhein recognize karta hai.

---

## 🔍 Apni Cookies kaise dekhein?

1. **Browser open karo (e.g. Chrome ya Firefox)**
2. Right-click karo kisi page par → **Inspect / Developer Tools** open karo
3. **Network tab** pe jao
4. Page ko refresh karo
5. Ab kisi request pe click karo → aur **Cookies tab** mein tumhein dikh jayega ke browser ne kya cookie bheji hai aur server ne kya cookie di hai

---

### 🛠 Penetration Testing Tip:

* **Session hijacking** test karne ke liye cookies ka access lena bohot zaroori hota hai
* **Cookie tampering** se tum authorization bypass ya role escalation test kar saktay ho
* Agar **cookie mein koi predictable value ya base64 encoded data** ho — toh samajh jao testing ka gate khul gaya 😈

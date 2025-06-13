# 🔍 Grep Match Kya Hota Hai?
Grep Match ka kaam hota hai:
Check karna ke response main koi specific word ya message "maujood" hai ya nahi.

Yani agar tum "Incorrect password" ko match karwate ho, to Burp check karega:
Kis response main yeh phrase aayi, aur kis main nahi aayi.

👣 Step-by-Step Tariqa:
1️⃣ Burp Intruder main jao → Grep – Match tab open karo
(default tab hoti hai)

2️⃣ "Add" pe click karo
Ek box khulega

Usmein likho:
Incorrect password
Ya jo bhi tum response main dhoondhna chahte ho

3️⃣ Attack chalao
✅ Result Analysis (Grep Match column):
Password Tried	Grep Match Column
- 123456	✔ Incorrect password
- root123	✔ Incorrect password
- qwerty123	❌ (blank) ✅

🟢 Jab kisi row mein match NA ho (i.e. ❌):
➡️ Matlab woh hi response alag tha, ho sakta hai login success hua ho.

### 🎯 Real-World Example:
Tum 100 passwords try kar rahe ho, aur har response main:
Incorrect password
Achanak ek row aayi jismein:

- Welcome back carlos! Aur
- "Incorrect password" match NA hua

✅ Grep Match wahan batayega: ❌
👉 Samajh jao: Yeh password sahi tha

### Grep Match
- Jab sirf ye check karna hoo ky word hai ya nahi too yeh use karo
- Jab sirf yeh krna hoo ky error hai ya nhi too yeh use karo

**Bhai honestly, penetration testing mein Grep Match bohot tez aur smart tool hai — agar error message fixed ho to match karlo,
aur agar response dynamic ho to extract better hota hai.**

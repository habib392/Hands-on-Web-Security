# GREP-EXTRACT

### ✅ Purpose:
Ye option use hota hai Burp Intruder main, jisse tum response ka specific hissa extract karke dekh sako —
Agar kisi response main ek specific error message NA ho, to samjho kuch different hua hai (e.g., login success).

**👣 Step-by-Step Samajh:**
1️⃣ Intruder main jao → Grep – Extract tab open karo
2️⃣ Run a normal login request → response check karo
Response main dekho:
Incorrect password ya Invalid credentials
(jo bhi consistent error ho, usko select karo)

3️⃣ Us error message ko highlight karo → "Add" button pe click karo
4️⃣ Attack run karo
Attack start hote hi Intruder main ek naya column aayega
👉 Is column ka naam hoga: Grep Extract

**🔍 Result Analysis:**
🟥 Agar sab rows main Incorrect password likha aaye:
➡️ Matlab password wrong tha

✅ Agar kisi ek row main blank ya different aaya:
➡️ Woh hi sahi password hai!
Kyunkay successful login main error message nahi hota

**📌 Example:**
Password Tried	Grep Extract Column
- 123456 - Incorrect password
- admin123	- Incorrect password
- carlos123	- blank ✅

➡️ carlos123 is correct password!

**Simple si baat** yeh hai ky Grep-Extract ius waqt use krna chahie jab respone column main haar dafa errors change hoty hoon jaisy
- Invalid username or password.
- Invalid password
- Too many login attempts
- Welcome back Carlos!

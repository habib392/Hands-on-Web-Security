✅ Aapka test payload:

<b>Khan</b>

🔍 Ab kya dekhna hai?

🔸 Case 1:

Aap comment submit karte ho <b>Khan</b>
🔁 Page refresh karte ho
📄 Output aata hai: Khan (bold)

➡️ Matlab: Website ne aapka HTML code sanitize nahi kiya.
✅ Website may be vulnerable to XSS.

---

🔸 Case 2:

Aap comment submit karte ho <b>Khan</b>
🔁 Page refresh karte ho
📄 Output aata hai: <b>Khan</b> (text hi show ho raha hai, bold nahi)

➡️ Matlab: Website ne aapka HTML escape kar diya
❌ Probably not vulnerable.

---

🤔 Ab XSS tester ban'nay ka next step kya?

Agar HTML tag render ho raha hai, matlab browser ne usay process kiya — toh aap next step mein XSS payload try kar sakte ho jaise:

**<script>alert('XSS')</script>**

Agar ye bhi chal gaya (popup aa gaya) toh:

💥 Website confirmed vulnerable to Stored XSS.

---

### 💡 Tip (Penetration Testing Use):

**<b>, <i>, <u>, <h1>, <a href>** jaise harmless HTML tags ek tester check karta hai taake:

Website sanitize karti hai ya nahi

Escape characters lagati hai ya nahi

Kya user input page pe raw HTML ban ke wapas aa raha hai
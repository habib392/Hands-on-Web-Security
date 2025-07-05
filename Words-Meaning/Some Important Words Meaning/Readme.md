✅ 1. Render (رینڈر کرنا)

Matlab: Kisi cheez ko screen par dikhana ya tayar karna (output).

Examples:

Browser HTML/JS/CSS ko render karta hai → web page display hota hai.

XSS payload agar <script>alert(1)</script> render ho jaye to attack successful hai.



---

✅ 2. Evaluate (ایویلیویٹ کرنا)

Matlab: Kisi cheez ka jaiza lena, test karna, ya uski value ya condition check karna.

Examples:

x == 5 → yeh evaluate karega ke x ka value 5 hai ya nahi.

Penetration testing mein input ya logic ko evaluate kiya jata hai ke wo secure hai ya vulnerable.



---

✅ 3. Filter (فلٹر کرنا)

Matlab: Galat, khatarnaak, ya unwanted data ko rokna ya hata dena.

Examples:

Input filter hone ka matlab hai user ke <script> jaise XSS payloads block ho jayein.

SQL Injection ya HTML injection roknay ke liye filters lagaye jaate hain.



---

✅ 4. Expression (ایکسپریشن)

Matlab: Aisi cheez jo kisi value ya condition ko show kare.

Examples:

2 + 2, x > 5, user == 'admin' → yeh sab expressions hain.

Security filters logical expressions evaluate karte hain jaise if input.contains("<script>").



---

✅ 5. Parse (پارس کرنا)

Matlab: Kisi data ko read karna, usay breakdown karna aur uski structure samajhna.

Examples:

Browser HTML parse karta hai → tags, attributes samajhta hai.

Server agar malicious input ko galat tarah parse kare to injection ho sakta hai (e.g. SQLi, XSS).



---

✅ 6. Framework (فریم ورک)

Matlab: Tayyar tools aur rules ka system jisme tum apna kaam fast aur asaani se kar sakte ho.

Examples:

Django, Laravel, React = development frameworks

Metasploit, Burp Suite = penetration testing frameworks



---

✅ 7. Sort (سورٹ کرنا)

Matlab: Cheezon ko order mein lagana — chhoti se bari ya bari se chhoti.

Examples:

sort(5, 2, 9, 1) → output: 1, 2, 5, 9

Burp Suite mein responses ko status code ke mutabiq sort karna.

Nmap scan results ko port number ke hisaab se sort karna.
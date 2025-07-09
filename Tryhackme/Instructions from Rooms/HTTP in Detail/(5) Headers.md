## 🔹 Headers kya hotay hain?

**Headers** wo **extra info** hoti hai jo tum **request bhejte waqt** ya **response lete waqt** exchange karte ho.
Bina headers ke bhi website chalti hai — lekin **thik tarah se kaam nahi karti.**
Headers basically batatay hain ke:
**“Yeh browser hai, itna data bhej raha hoon, yeh format chahiye, yeh website chahiye, etc.”**

---

## 🔸 Common **Request Headers** (Jo client → server ko bhejta hai)

1. **Host:**
   Agar server par multiple websites hoon, toh **host header batata hai** ke kis website ka content chahiye.
   Example: `Host: tryhackme.com`

2. **User-Agent:**
   Yeh browser ka naam aur version hota hai. Server decide karta hai ke **konsa layout ya features dikhayein.**
   Example: `User-Agent: Firefox/87.0`

3. **Content-Length:**
   Jab tum form ya data POST karo, toh batana padta hai ke **kitna data bheja jaa raha hai**.

4. **Accept-Encoding:**
   Browser batata hai ke **kaunsi compression types** (gzip, deflate etc.) support karta hoon — taake data compress ho kar aaye.

5. **Cookie:**
   Browser apne pass save ki gayi cookies server ko bhejta hai — jaisay login session, ya user preferences.

---

## 🔸 Common **Response Headers** (Jo server → client ko bhejta hai)

1. **Set-Cookie:**
   Server kehta hai: “Yeh info save rakh lo, agli dafa mujhe bhejna.”
   Example: login session ID, cart items waghera.

2. **Cache-Control:**
   Server batata hai ke browser **kitni der tak is data ko cache kar sakta hai** — yani baar baar request na bheje.

3. **Content-Type:**
   Server batata hai ke **kis type ka data bhej raha hoon** — HTML, image, video, CSS, JavaScript, etc.

4. **Content-Encoding:**
   Yeh batata hai ke data ko **kis method se compress** kiya gaya hai — taake browser usi hisaab se decode kare.

---

### 🛠 Penetration Testing Tip:

* **User-Agent** spoof karke tum bot detection ya feature access test kar saktay ho
* **Host Header Injection** se website impersonation ya cache poisoning try ki ja sakti hai
* **Cookie tampering** se authentication bypass ya session hijacking test ki ja sakti hai
* **Cache-Control** misconfig hone par sensitive data cache ho sakta hai
* **Content-Type** ko manipulate kar ke XSS ya file upload bypass bhi test kiya ja sakta hai
Client-side aur server-side web application ke do parts hote hain. Client-side ka matlab hota hai browser (user ka device) pe chalne wala code, jaise HTML, CSS, JavaScript. Server-side wo hota hai jo backend pe server par process hota hai, jaise database access, authentication, etc. Client-side fast hota hai, user ko quick response milta hai, lekin zyada secure nahi hota. Jab koi hacker browser ka code dekh sakta hai, to wo manipulate kar sakta hai. Security sirf server-side pe strong hoti hai.

### 📝 15 Lines

1. Client-side ka matlab hota hai user ke browser main chalne wala code.

2. Server-side ka matlab hota hai server (backend) pe chalne wala code.

3. Client-side main HTML, CSS aur JavaScript hoti hai.

4. Server-side main PHP, Python, Node.js, database waghera hotay hain.

5. Client-side fast hota hai, response jaldi milta hai.

6. Lekin client-side secure nahi hota.

7. Hacker browser ka code inspect kar sakta hai.

8. JavaScript ko bypass kar ke hacker form ya request modify kar sakta hai.

9. Server-side hi asli decision leta hai, jaise login allow karna ya data dena.

10. Sirf client-side validation karna risky hota hai.

11. Kabhi bhi sensitive cheez client-side pe mat rakho.

12. Agar login ya price client-side pe ho, hacker usay change kar sakta hai.

13. Server-side pe validation aur authorization zaroor honi chahiye.

14. Client-side sirf user experience ke liye use karo (layout, colors, animations).

15. Security ka kaam server ka hota hai, browser ka nahi.

### 💻 System Based Example:

Client-side: Aik shopping website ka "Add to Cart" button jab click hota hai, to JavaScript se product cart main dikhata hai.

Server-side: Jab user "Place Order" karta hai, server pe ja kar check hota hai kya user logged in hai, item available hai, phir order process hota hai.

### 🌍 Real-Life Example:

Client-side: ATM screen pr tum pin enter kartay ho, screen tumhara interface hai.

Server-side: Jab tumhara pin check hota hai aur balance nikalta hai, wo server bank ke backend system main hota hai.

--- 

Jab tu Facebook ya WhatsApp pe apny bhai ko message karta hai, to:

🔹 Client-side kya karta hai?

Jo tu likhta hai message (like “Salam bhai”), wo tera mobile ya browser pe hota hai.

Jo screen pe dikh raha hota hai (typing, emojis, colors), wo sab client-side ka kaam hai.

Yani tera phone ya browser woh kaam karta hai jo sirf tujhe dikhana hai — interface wala kaam.


🔹 Server-side kya karta hai?

Jab tu send button dabata hai, tera message WhatsApp/Facebook ke server tak jata hai.

Server phir check karta hai: kis ko bhejna hai? user valid hai? block to nahi?

Phir wo message tera bhai ke phone tak server ke zariye pohanchata hai.

---

🎯 Asaan Lafzon Mein:

Client-side = Tera mobile ka kaam (likhna, dikhana, button dabana).

Server-side = Facebook/WhatsApp ka server ka kaam (message bhejna, save karna, aagay forward karna).

---

🔐 Penetration Testing mein kya faida?

Agar tu sirf client-side validate kare (e.g. message “allowed” hai ya nahi), to attacker JavaScript change karke har cheez bypass kar sakta hai.
Lekin agar server pe bhi proper check ho raha ho, to attacker kuch nahi kar sakta.

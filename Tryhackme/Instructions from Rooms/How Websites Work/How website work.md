## How Website Work

Jab tum kisi website pe jaatay ho, jaise Chrome ya Safari se, toh tumhara browser aik request bhejta hai kisi door kahin duniya ke kone mein mojood server ko. Ye server asal mein aik powerful computer hota hai jo websites ko handle karta hai.

Phir ye server tumhari request ka jawab deta hai — matlab uss page ki sari malomaat bhejta hai — aur tumhara browser uss malomaat ko samajh kar tumhare samne ek website ki shakal mein dikhata hai.

Ek website do main parts se milkar banti hai:

Front End (Client-Side) – Ye woh hissa hota hai jo tumhare browser mein dikh raha hota hai, jaise text, buttons, colors waghera. Ismein HTML, CSS, JavaScript use hoti hain.

Back End (Server-Side) – Ye website ka dimaag hota hai jo tumhari request process karta hai, data laata hai, update karta hai, aur front end ko bhejta hai. Ismein languages hoti hain jaise PHP, Python, Node.js, Ruby waghera.

Simple alfaaz mein:
Tum request karte ho (jaise: “bhai mujhe page dikhao”), server reply karta hai (jaise: “ye lo page”).
Tumhara browser uss reply ko samajh ke tumhe website dikhata hai.

![XSS Screenshot](Tryhackme/Instructions from Rooms/How Websites Work/Tryhackme22.png)

---

## What is Servers??
🔹 Server asal mein aik special computer hota hai
Ye 24/7 chalu rehta hai, fast hota hai, aur uska kaam sirf dusre logon ki requests ka jawab dena hota hai (jaise tumhari browser ki request).

🔹 Lekin aik server poori duniya ko handle nahi kar sakta
Socho agar Facebook ya Google sirf 1 server pe chaltay, toh wo 2 second mein crash ho jaatay — itni saari duniya ki requests ka pressure bardasht nahi kar sakta.

🔹 Isliye companies kya karti hain?
Wo server farms ya data centers banati hain — jaahan hazaaron servers ek saath chal rahe hote hain.
Jaise:

Google ke paas apne data centers hain US, Europe, Asia mein.

Facebook ke paas bhi khud ke server farms hain.

Aur agar tum website host karna chaaho, toh tum bhi kisi company se server rent pe le sakte ho — jaise:

- Hostinger
- DigitalOcean
- AWS (Amazon Web Services)
- Hetzner
- Google Cloud

Yani server aik computer hi hota hai, lekin bohot saare servers mil ke kaam kartay hain — taakay speed bhi achhi ho, load bhi divide ho,aur backup bhi ho.

---

### Is Server is a PC??

#### Simple example:
Tumhara khud ka PC hai ghar mein. Lekin agar tum chaho ke duniya bhar ke log tumhari website ko 24/7 access kar saken, toh:

Tumhara PC 24/7 chalu rehna chahiye

Fast internet chahiye

Security chahiye

Backup chahiye

Yeh sab mushkil hai na?

Isliye companies jaise Hostinger, Namecheap, DigitalOcean ke paas already powerful servers hote hain — aur wo tumhe space ya pura server rent pe deti hain.
Hostinger kya karta hai?
Uske paas Europe ya US mein bohot saare powerful computers (servers) hote hain.

Tum usmein thoda sa space le lete ho — jaise 1 website ke liye.

Tum monthly ya yearly uska kiraya dete ho — jaise 500 rupay mahina.

Matlab server khareedna nahi padta, bas use karne ka paisa dena padta hai. Aur wo server kisi aur jagah hota hai, tumhara kaam online ho jata hai.

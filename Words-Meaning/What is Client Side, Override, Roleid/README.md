# 🧱 Client-side kya hoti hai?

Client-side wo hoti hai jo user ke browser mein chalti hai.
Yani:

HTML

CSS

JavaScript

Forms

Cookies

Jo cheezein tu "Inspect Element" se dekh sakta hai


### ✅ Example:
Agar form mein likha ho roleid=1, aur wo browser mein visible ya editable hai, to wo client-side control hai.
Danger: Agar developer ne sirf yahin pe check lagaya aur backend pe kuch nahi, to attacker usko change karke kuch bhi kar sakta hai!

## 🧑‍💼 roleid: 1 se roleid: 2 karne ka kya effect hota hai?

Yeh developer pe depend karta hai, lekin aksar applications mein:

- roleid = 1 → normal user

- roleid = 2 → admin user


Agar tu "roleid":1 ko "roleid":2 mein tamper karta hai, aur server is change ko accept kar leta hai, to:

Tu admin privileges le leta hai bina permission ke! 🔓🔥

## 🔁 Override ka matlab kya hota hai?

Override ka matlab hota hai badalna ya replace karna kisi cheez ko.

Yeh synonyms (mutaradif) samajh lo:

Override = Change = Modify = Replace = Manipulate
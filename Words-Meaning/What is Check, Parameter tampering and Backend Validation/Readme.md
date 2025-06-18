# 🔍 1. Check kya hota hai?

"Check" ka matlab hota hai kisi cheez ko verify karna — jaise:

Username/password sahi hai ya nahi? ✅

User ka role admin hai ya user? 👤

Token ya OTP valid hai ya fake? 🔐

Yeh system ke rules hote hain jo har request pe check karte hain:
"Kya ye user allowed hai? Kya ye sahi cheez bhej raha hai?"

# 🔧 2. Parameter Tampering kya hota hai?

"Parameter" ka matlab hota hai wo data jo browser se request mein bheja jata hai,
jaise login form mein:

**POST /login
username=wiener&password=peter**

"Tampering" ka matlab hai usi data ko change kar dena — jaise BurpSuite se modify kar lena.

### 🔓 Example:

Tum client side pe form submit kar rahe ho:

**POST /change-role
role=user**

Lekin BurpSuite se change kar ke:

**role=admin**

Agar backend check nahi karta ke sirf admin ko admin role mil sakta hai,
toh attacker ban gaya admin — yeh hota hai parameter tampering attack.

# 🚨 3. Missing Backend Validation kya hota hai?

Yeh sabse dangerous galti hoti hai!

Developer front-end (HTML/JavaScript) mein kuch validate karta hai:

"User ne password likha hai ya nahi?"

Lekin backend (server-side) pe wo dobara check hi nahi karta!

**❗Problem:**

Frontend check toh attacker disable kar sakta hai (browser ya BurpSuite se).

Agar backend kuch verify nahi kar raha, toh attacker kuch bhi bhej dega — aur accept ho jayega!

### 📌 Real Example:

Case: Change Password Function

Form:

Current password

New password

Confirm new password

Attacker ne frontend form se current_password hata diya aur BurpSuite mein request bhej di.

Agar backend ne dobara check nahi kiya ke current password sahi tha ya nahi,
toh attacker ne bina old password jaane password change kar diya. 😱

## 🔐 Summary:

Term	Asaan Matlab

**Check**	System ka rule: "Yeh user ya data sahi hai ya nahi"

**Parameter tampering** Request ka data change karna — jaise role, price, password

Missing **backend validation**	Server ne dobara verify hi nahi kiya — sirf frontend pe bharosa kiya
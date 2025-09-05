**IDOR (Insecure Direct Object Reference)** ek access control ki vulnerability hai. Yeh tab hoti hai jab developer server ke andar kisi “object” ka direct reference expose kar deta hai — object matlab kuch bhi ho sakta hai: ek file, ek user, ek account number, ya koi aur cheez.

Problem yeh hoti hai ke agar application proper check na kare ke current user ka woh object hai ya nahi, to attacker sirf URL ya parameter change karke doosron ka data access kar leta hai.

Example:
Tu apne bank account main login karta hai aur tujhe ek URL milta hai:

```
https://bank.thm/account?id=111111
```

Ye teray account ka data show kar raha hai. Ab agar koi banda `id=222222` kar de aur site ne check hi na kiya ke yeh account tera hai ya nahi, to woh doosre user ka bank data dekh lega.

Yahan dikkat “direct object reference” nahi hai, asal problem yeh hai ke **application validate hi nahi karti ke user jis account ko access kar raha hai woh uska hai ya nahi.** Isi ko IDOR bolte hain.


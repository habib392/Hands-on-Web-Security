Har website main kuch pages hote hain jo aam visitors k liye nahi hote, sirf admins ya authorized users k liye hote hain. Jaise ek admin hi users ko manage kar sakta hai, koi normal visitor nahi.

Agar normal visitor in hidden/protected pages tak pohanch jaye, to iska matlab hai **Access Control broken hai.**

Iska nuksan yeh ho sakta hai:

* Users ki private/sensitive information dekh lena
* Unauthorized functionality (jo sirf admin kar sakta tha) use kar lena

Seedhi baat: **Broken Access Control attacker ko authorization bypass karne deta hai.** Iska matlab woh data dekh sakta hai ya kaam kar sakta hai jo usay karna allowed nahi.

Ek real example bhi diya gaya: 2019 main ek vulnerability YouTube main mili thi jahan attacker ek private video k frames alag alag download kar k thoda reconstruct kar leta tha. Jab user video ko private set karta hai to uska expectation yeh hota hai ke koi bhi access na kar sake. Isliye isko Broken Access Control mana gaya.


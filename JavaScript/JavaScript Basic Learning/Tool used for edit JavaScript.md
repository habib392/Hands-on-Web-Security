# ✅ JavaScript agar HTML ke andar ho **<script>...</script>**

Aur aap usay edit karna chahtay ho (testing ya payload inject karne ke liye)
Toh yeh 3 common methods hain:

### 🔧 1. Burp Suite ka use (intercept aur modify):

✅ Yeh jab useful hota hai:

Jab user ka input (comment, search, form) JavaScript mein inject ho raha hota hai.

Aap <script>alert(1)</script> jaisa payload daal kar Burp mein intercept karke dekh saktay ho response mein aa raha hai ya nahi.

### 🧠 Example:

1. Website pe comment karo: **<script>alert('XSS')</script>**

2. Burp Suite mein request intercept karo.

3. Dekho request mein yeh payload ja raha hai ya nahi.

4. Response mein dekho JavaScript ke andar woh payload reflect ho raha hai ya nahi.

➡️ Agar reflect ho raha hai, XSS test karo!

### 🛠️ 2. Browser Developer Tools (F12):

✅ Jab useful hota hai:

Jab aap locally dekhnay chah rahe ho JavaScript kis jagah execute ho rahi hai.

JavaScript code samajhna ho (DOM-based XSS find karna ho).

### Steps:

1. Website open karo.

2. Right click → "Inspect" (ya F12).

3. "Sources" ya "Elements" tab mein jao.

4. **<script>...</script>** code dhoondo.

5. Wahin pe code edit bhi kar sakte ho testing ke liye.

➡️ Yeh browser side testing ke liye acha hai.
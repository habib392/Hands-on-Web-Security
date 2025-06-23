# ✅ JavaScript Beginner Program (for XSS Learners)

## 🔹 HTML + JavaScript Example

```html
<!DOCTYPE html>
<html>
<head>
  <title>My First JS Program</title>
</head>
<body>

<h1>Welcome!</h1>
<button onclick="showMessage()">Click Me</button>

<script>
  function showMessage() {
    alert("Hello Habib! You're learning JavaScript!");
  }
</script>

</body>
</html>```

---

🔍 Is Program Mein Kya Use Hua Hai?

Element	Kya hai?

<!DOCTYPE html>	
HTML5 ka standard	Browser ko batata hai ke HTML5 use ho raha hai

<html> ... </html>	HTML document ka structure	Saari website isi ke andar hoti hai

<head>	Hidden info jaise title waghera	User ko direct nahi dikhta

<title>	Page ka naam browser tab mein	Tab mein jo naam dikh raha hota hai

<body>	Page ka visible content	User ko jo dikhta hai wo sab yahan hota hai

<h1>	Heading tag	Badi heading ke liye

<button>	Button	Jab click karo to kuch ho
onclick="showMessage()"	Button click event	JavaScript function run karta hai

<script>	JavaScript code likhne ke liye	Iss tag ke andar JS hoti hai

function showMessage()	JavaScript function	Ek kaam define karne ke liye use hota hai

alert("...")	Pop-up message	User ko ek box mein message dikhata hai


🎯 Flow When Button is Clicked

1. User button pe click karta hai.

2. onclick JavaScript function run karta hai.

3. Pop-up dikh jata hai using alert().

🔐 Connection with XSS Attacks

XSS payload like alert("XSS") pop-up show kare to:

JavaScript run ho rahi hai ✅

Page vulnerable hai ✅

Advanced payloads inject ho sakte hain 

---

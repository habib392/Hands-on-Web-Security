# ✅ Lesson 3 — JavaScript mein "Variable" kya hota hai?

### 📌 Variable matlab?

Jab humein koi cheez ya value yaad rakhni hoti hai — jaise:

- Naam

- Umar (age)

- Sheher ka naam

toh hum uske liye ek box banate hain — aur us box ka naam rakh lete hain. Isi box ko variable kehte hain.

Jaise school ka bag — tum usmein pencil, notebook, lunch rakhte ho. Usi tarah JavaScript mein bag jesa box hota hai jiska naam hota hai, aur usme koi value rakh dete hain.

### 🔤 Example:

var name = "Habib";

Yahan:

var ka matlab hai: main ek box bana raha hoon

name box ka naam hai

= ka matlab hai: is box mein yeh cheez daal raha hoon

"Habib" wo cheez hai jo daal rahe ho

Matlab: "Habib naam ki value ko 'name' naam ke box mein daal do."

### 🎉 Dusra example:

var age = 18;

Yahan:

Ek box banaya jiska naam age hai

Usmein 18 daal diya


🖨️ Output kaise check karein?

console.log(age);

Yeh likhne se wo value screen par nahi — console mein print hoti hai. Console wo jagah hai jahan developer check karta hai ke code theek chal raha hai ya nahi.

💡 Full example jo tum browser mein chala sako:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Simple JavaScript</title>
</head>
<body>

<h1>Simple Program</h1>
<button onclick="show()">Click Me</button>

<script>
  function show() {
    var name = "Habib";
    var age = 18;

    console.log("Mera naam hai: " + name);
    console.log("Meri umar hai: " + age);
  }
</script>

</body>
</html>


---

🧪 Try karo:

1. Code ko run karo (Notepad mein likho aur .html file banao)


2. Right-click → Inspect → Console tab khol lo


3. Button press karo → Dekho kya print hota hai


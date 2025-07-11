**JavaScript (JS)** duniya ki sabse mashhoor coding languages mein se ek hai. Iska kaam hai **web pages ko interactive banana**.

* **HTML** website ka structure banata hai.
* **JavaScript** website mein action aur response dalta hai.

Agar JavaScript na ho, toh website **sirf static** hoti — sirf text aur images, koi button click ka effect nahi hota, koi animation nahi hoti.

JavaScript se page real-time mein change ho sakta hai — jaise:

* Button pe click karne se uska color change ho jana
* Animation chalna
* Text update ho jana

---

JavaScript ko page ke andar do tareeqon se likha ja sakta hai:

1. Seedha page ke andar likho:

```html
<script>
  // JavaScript code yahan aata hai
</script>
```

2. Ya bahar se file ka link do:

```html
<script src="/location/of/javascript_file.js"></script>
```

---

### Example:

Ye code HTML page par `id="demo"` wale element ka text change kar deta hai:

```js
document.getElementById("demo").innerHTML = "Hack the Planet";
```

---

### Event Example:

HTML element ke andar kuch events hote hain, jaise:

* `onclick` – jab button pe click ho
* `onhover` – jab mouse le jao

Ye code button pe click karne par text change karta hai:

```html
<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>Click Me!</button>
```

Yeh **onclick** JavaScript tag ke andar bhi define kiya ja sakta hai, na ke sirf button mein.

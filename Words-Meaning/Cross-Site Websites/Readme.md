## 🔁 **Cross-Site Websites ka matlab kya hota hai?**

**Cross-site** ka matlab hota hai:

> "Do alag websites jin ka **origin** alag ho"
> Origin = `scheme (http/https)` + `domain` + `port`

---

## 📌 **Simple Example:**

| Website                  | Origin                            |
| ------------------------ | --------------------------------- |
| `https://habib.com`      | ✅ Yeh tumhari own site hai        |
| `https://google.com`     | ❌ Cross-site                      |
| `http://habib.com`       | ❌ Cross-site (scheme change hua)  |
| `https://api.habib.com`  | ❌ Cross-site (subdomain alag hai) |
| `https://habib.com:8080` | ❌ Cross-site (port alag hai)      |

---

## 🎯 **Cross-Site ka Real World Example:**

Tum login ho `https://bank.com` pe
Aur koi attacker tumhe `https://evil.com` pe le jata hai

Agar `evil.com` ki site try kare bank.com se data lene ki →
Browser kahega:

> ❌ "Cross-site request hai. Same-Origin Policy allow nahi karti"

---

## 🧠 Summary

> "Jab bhi do websites ka **domain ya scheme ya port** alag ho — woh **cross-site** kehlati hai"

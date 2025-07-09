### Jab hum kisi website ko kholte hain

Toh tumhara browser **request bhejta hai server ko** — jaise HTML file, image, video ya kuch aur maangta hai.
Lekin browser ko yeh bhi batana padta hai ke **kis cheez ko aur kahan se maangna hai** — aur yahan pe **URL** ka kaam aata hai.

---

### URL kya hota hai? *(Uniform Resource Locator)*

Jo link tum browser mein likhtay ho — jaise `https://google.com` — wohi URL hai.
Yeh ek **pura address hota hai** jo browser ko batata hai ke kis resource ko kaise lena hai.

---

### URL ke parts:

1. **Scheme:**
   Yeh batata hai ke **kaunsa protocol** use ho raha hai — jaise `http`, `https`, `ftp` waghera.

2. **User:**
   Kabhi kabhi tumhe server pe login karna hota hai. URL ke andar **username\:password** daal ke bhi login ho sakta hai.
   Example: `ftp://username:password@ftp.example.com`

3. **Host:**
   Yeh hota hai **server ka address** — domain name (jaise google.com) ya IP address (jaise 192.168.1.1)

4. **Port:**
   Server pe har service ek **port number** pe hoti hai. HTTP usually **80**, HTTPS usually **443** use karta hai.
   Lekin koi bhi port ho sakta hai **1 se 65535** ke darmiyan.

5. **Path:**
   Server pe **kis file ya folder ko access** karna hai — woh yahan likha hota hai.
   Jaise `/index.html` ya `/images/logo.png`

6. **Query String:**
   Yeh extra information hoti hai jo request mein bhejte ho.
   Jaise: `/blog?id=1` — iska matlab hai `blog` naam ka article chahiye jiska ID 1 hai.

7. **Fragment:**
   Page ke **specific hisse** pe le jata hai.
   Jaise agar page bohat lamba hai, toh `#section2` tumhein sida second part pe le jaayega.

---

### Request kaise banta hai?

Agar tum command line se ya manually request bhejna chaho, toh sirf **ek line se** bhi request ban jata hai:

```http
GET / HTTP/1.1
```

Yeh line server ko kehti hai:

* `GET` yani mujhe data chahiye
* `/` yani homepage chahiye
* `HTTP/1.1` yani jo protocol version use kar raha hoon

---

### 💡 **Penetration Testing Tip:**
Query strings, ports, aur path parameters ko **tamper** (badal) karke tum bugs jaise SQLi, IDOR, XSS ya file inclusion test kar saktay ho.
URL structure ko samajhna pen-testing ka **basic weapon** hai.

---

## 🔹 Browser sirf URL se kaam nahi karta

Agar tum chaho ke website tumhein **achha, detailed jawab de**, toh tumhein sirf URL nahi — **extra info** bhi deni padti hai.
Yeh extra info jo hoti hai, use kehte hain **headers**.

---

### 🔸 Example Request:

```http
GET / HTTP/1.1  
Host: tryhackme.com  
User-Agent: Mozilla/5.0 Firefox/87.0  
Referer: https://tryhackme.com/  
```

### 📖 Samjho har line kya kahti hai:

1. **`GET / HTTP/1.1`**

   * "GET" ka matlab: mujhe homepage chahiye (`/`)
   * "HTTP/1.1" batata hai kaunsa version use kar raha hoon

2. **`Host: tryhackme.com`**

   * Server ko bataya ja raha hai ke kis website ka homepage chahiye

3. **`User-Agent: Mozilla/5.0 Firefox/87.0`**

   * Yeh batata hai ke **kaunsa browser** use ho raha hai

4. **`Referer: https://tryhackme.com/`**

   * Batata hai ke user ne kis page se yeh current page open kiya

5. **Blank line**

   * HTTP request ka **khatam hone ka signal** hota hai

---

## 🔹 Ab server ka jawab dekho — Response:

```http
HTTP/1.1 200 OK  
Server: nginx/1.15.8  
Date: Fri, 09 Apr 2021 13:34:03 GMT  
Content-Type: text/html  
Content-Length: 98  

<html>  
  <head><title>TryHackMe</title></head>  
  <body>Welcome To TryHackMe.com</body>  
</html>  
```

### 📖 Response ki line-by-line samajh:

1. **`HTTP/1.1 200 OK`**

   * Server bhi HTTP 1.1 use kar raha hai
   * `200 OK` ka matlab: sab kuch sahi gaya

2. **`Server: nginx/1.15.8`**

   * Server ka software aur version bataya ja raha hai

3. **`Date: ...`**

   * Server kis date aur time par response de raha hai

4. **`Content-Type: text/html`**

   * Yeh batata hai ke data kis format mein aayega — yahan `HTML`

5. **`Content-Length: 98`**

   * Total size batata hai — yani kitna data mil raha hai

6. **Blank line**

   * Response yahan khatam ho gaya

7. **HTML content**

   * Jo tum browser mein dekhte ho — yeh actual page ka content hota hai

---

### 🔐 Penetration Testing Tip:

Headers se tum bohat kuch samajh saktay ho —

* **User-Agent spoofing**
* **Referer tampering**
* **Content-Type changes for XSS / file upload attacks**
  Aur response headers se server ka **software version detect** kar ke tum specific **vulnerability scan** kar saktay ho (jaise nginx ki known CVEs).



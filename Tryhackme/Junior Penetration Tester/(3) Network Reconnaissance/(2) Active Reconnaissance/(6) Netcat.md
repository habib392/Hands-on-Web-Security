Ab tum cyber security ke sab se mashhoor aur versatile tool par aa gaye ho: **Netcat (nc)**. Isko hackers ka **"Swiss Army Knife"** (sab-kuch-karne-wala-chaku) kaha jata hai kyunke yeh itna chota sa tool hai par is se hazaron kaam liye ja sakte hain.
Chalo isko asani se samajhte hain ke Netcat kya hai aur yeh Telnet se behtar kyun hai.

## 1. Netcat Kya Hai aur Yeh Do-Tarfa (Dual) Kaam Kaise Karta Hai?
Telnet sirf doosray servers se **connect** ho sakta tha (yani sirf client ban sakta tha). Lekin Netcat ki sab se bari khoobi yeh hai ke yeh dono kaam kar sakta hai:
 1. **Client Mode:** Kisi doosray server ke port se connect hona.
 2. **Server Mode:** Apne computer par kisi port ko open kar ke baith jana aur requests ka **intezar (listen)** karna.
Yeh TCP aur UDP dono protocols ko support karta hai. Iska modern version **Ncat** (jo Nmap ke sath aata hai) SSL encryption aur IPv6 ko bhi support karta hai, is liye yeh Telnet se hazaar guna behtar hai.
## 2. Netcat Se Banner Grabbing (Client Mode)
Netcat se banner grab karne ka tareeqa bilkul Telnet jaisa hi hai, bas command thori aasan hai:
```bash
nc MACHINE_IP PORT

```
Agar tum port 80 (HTTP) par connect ho kar manually request bhejoge:
```http
GET / HTTP/1.1
host: netcat

```
*(Yahan terminal mein Shift+Enter daba kar do baar Enter press karna parta hai).*
Toh server tumhein Telnet ki tarah hi response dega jahan tum Server: nginx/1.6.2 jaisa banner dekh kar version pata kar sakte ho. FTP (Port 21) ya SMTP (Port 25) par toh yeh connect hote ہی khud-ba-khud banner show kar deta hai.
## 3. Netcat Se Port Listen Karna (Server Mode) 🎧
Yeh Netcat ka sab se mazedar feature hai. Tum apne computer ko aik server bana sakte ho jo kisi bhi port par listen karega. Is ke liye command yeh hoti hai:
```bash
nc -vnlp 1234

```
### In Flags Ka Matlab Kya Hai? (Yaad rakhna zaroori hai)
 * **-l (Listen):** Netcat ko batata hai ke tum ne kisi se connect nahi hona, balkay khud server ban kar baithna hai.
 * **-p (Port):** Is ke aage port number likha jata hai (jaise 1234). *Yaad rahe, port number hamesha -p ke foran baad aayega.*
 * **-n (Numeric):** DNS resolution nahi karta (IPs ko names mein convert nahi karta), jis se command fast chalti hai.
 * **-v (Verbose):** Tumhein terminal par batata hai ke background mein kya chal raha hai (jaise jab koi connect hoga toh alert dega).
### 💬 Chat Room Banana:
Agar tum aik terminal mein nc -vnlp 1234 chalao (Server), aur doosray terminal (ya doosray computer) se nc SERVER_IP 1234 chalao (Client), toh dono ke darmiyan aik direct connection ban jayega. Ab tum aik taraf jo bhi type karoge, woh doosri taraf screen par nazar aayega! Cyber security mein iska use **Reverse Shells** lene ke liye bohot zyada hota hai.
> ⚠️ **Zaroori Baat:** Port number 1 to 1023 bohot sensitive (well-known) hote hain, is liye un par listen karne ke liye tumhein sudo (root privileges) chahiye hoti hain. 1024 se upar wale ports tum bina sudo ke bhi listen kar sakte ho.
> 

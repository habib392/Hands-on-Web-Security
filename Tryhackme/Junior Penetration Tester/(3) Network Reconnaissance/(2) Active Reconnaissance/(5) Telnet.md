**Task 5: Yeh section bohot hi interesting hai kyunke yeh tumhein cyber security ka aik bohot mashhoor concept sikhane laga hai: **Banner Grabbing** (Server ki software aur version info nikalna).
Chalo isko bilkul aasan lafzon mein samajhte hain:

## 1. Telnet Asal Mein Kya Hai?
Telnet 1969 mein banaya gaya aik bohot purana protocol hai jo remote computers (servers) ko command line ke zariye control karne ke liye use hota tha. Iska **default port 23** hota hai.
 * **❌ Sab se Bara Masla (Security Risk):** Telnet ka poora traffic **Cleartext** (plain text) mein jata hai. Agar tum telnet par username aur password likhoge, toh network par baitha koi bhi banda (jaise Wireshark use kar ke) tumhara password sukoon se dekh sakta hai.
 * **✔️ Modern Alternative:** Aaj kal iski jagah **SSH (Secure Shell)** use hota hai jo saare traffic ko encrypt (secure) kar deta hai.
## 2. Hackers Telnet Kyun Use Karte Hain? (Banner Grabbing)
Puranay aur khatarnak hone ke bawajood, Telnet client hackers ke liye aik bohot kaam ki cheez hai. Kyunke yeh **TCP protocol** par kaam karta hai, is liye tum isko kisi bhi TCP port se connect kar ke server ka javab check kar sakte ho.
Isi cheez ko hum **Banner Grabbing** kehte hain. Jab aap kisi server ke port se connect hote ho, toh server pehli request par apna aik "intro" bhejta hai jise **Banner** kehte hain. Is banner mein aksar server ka naam aur uska **exact version** likha hota hai.
## 3. Practical Example se Samjho (Web Server scanning)
Upar diye gaye terminal example mein hacker ne port 80 (HTTP) par telnet chalaya:
```bash
telnet MACHINE_IP 80

```
Connect hone ke baad hacker ne manually aik choti si HTTP request type ki:
```http
GET / HTTP/1.1
host: telnet

```
*(Aur do baar Enter press kiya)*
Server ne javab mein bohot saara data bheja (Headers), lekin hacker ki nazar sirf aik line par thi:
> **Server: nginx/1.6.2**
> 
### As a Hacker Tumhein Iska Kya Faida Hua?
Tumhein pata chal gaya ke target server par **Nginx** chal raha hai aur uska version **1.6.2** hai. Ab tum seedha Google par jaoge, ya **Exploit-DB** aur **CVE** (Common Vulnerabilities and Exposures) ke databases check karoge ke *"Kya Nginx 1.6.2 mein koi purani vulnerability ya bug hai jis se isko hack kiya ja sake?"* Agar koi exploit mil gaya, toh server par control haasil karna aasan ho jayega!
## 4. Mukhtalif Ports par Banner Grabbing
Yeh technique har TCP service par kaam karti hai:
 * **FTP (Port 21):** Yahan toh request bhejni bhi nahi parti, jaise hi telnet connect hoga, FTP server khud hi apna version show kar dega.
 * **Mail Server (SMTP - Port 25):** Yahan aap connect ho kar mail server ka version dekh sakte hain.
## 5. ⚠️ Telnet Ki Limitation (Modern Encrypted Sites)
Aaj kal ki modern websites HTTPS (Port 443) use karti hain, jo encrypted hoti hain. Telnet encrypted data ko samajh nahi sakta, is liye yeh HTTPS par fail ho jata hai.
Encrypted servers par banner grab karne ke liye hum doosray tools use karte hain:
 * curl --head https://MACHINE_IP
 * openssl s_client -connect MACHINE_IP:443

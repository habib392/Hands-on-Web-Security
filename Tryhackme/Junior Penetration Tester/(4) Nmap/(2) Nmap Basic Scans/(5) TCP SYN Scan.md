Chalo ab **Task 5: TCP SYN Scan (-sS)** ka poora postmortem karte hain.
## 🔬 TCP SYN Scan (-sS) Kya Hai aur Yeh Kyun Khaas Hai?
TCP SYN Scan ko cyber security ki duniya mein **"Stealth Scan"** ya **"Half-Open Scan"** bhi kehte hain. Yeh Nmap ka sab sy favorite aur default scan hai (agar tumhare paas root ya sudo privileges hon).
Pichlay task mein hum ne dekha tha ky **TCP Connect Scan (-sT)** target ky sath poori dosti yaani **TCP 3-Way Handshake** complete karta hai. Lekin SYN scan bohot chalak hai, yeh dosti ka haath barhata hai aur jaise ہی samnay wala haath aagay karta hai, yeh apna haath peechay kheench leta hai!
## 🔄 Deep Working: Backend Par Packets Kaise Move Karte Hain?
Jab tum terminal par nmap -sS <target_ip> chalate ho, toh open aur closed ports par alag alag behaviors hote hain:
### 1. Open Port Ka Behavior (The Half-Open Trick)
 * **Step 1 (Nmap \rightarrow Target):** Nmap target machine ky ek specific port par ek packet bhejta hai jismey **SYN flag** set (1) hota hai. Yeh keh raha hota hai: *"Kya mein connection shuru karoon?"*
 * **Step 2 (Target \rightarrow Nmap):** Agar wo port open hai aur wahan koi service chal rahi hai, toh target machine jawab mein **SYN-ACK packet** bhejti hai. Iska matlab hota hai: *"Haan, port open hai, a jao connection bana lo."*
 * **Step 3 (Nmap \rightarrow Target):** Ab standard rules ky mutabik Nmap ko ACK bhej kar connection mukammal karna chahiye tha (jaise connect scan mein hota hai). Lekin Nmap chalaki karta hai! Nmap ko apna jawab (SYN-ACK) mil chuka hota hai aur pata chal jata hai ky port open hai. Is liye connection complete krny ky bajaye Nmap foran ek **RST (Reset) packet** bhej deta hai. Is sy connection handshake poora hone sy pehle hi beech mein toot jata hai.
### 2. Closed Port Ka Behavior
 * **Step 1 (Nmap \rightarrow Target):** Nmap ne SYN packet bheja.
 * **Step 2 (Target \rightarrow Nmap):** Agar port par koi service nahi hai (closed hai), toh target machine ka operating system gusse mein foran ek **RST-ACK packet** bhejta hai, jiska matlab hota hai: *"Yahan koi nahi hai, connection band karo."*
## ⚔️ Connect Scan (-sT) vs SYN Scan (-sS) Ka Muqabla
In dono ka farq samajhna bohot zaroori hai:
| Feature | TCP Connect Scan (-sT) | TCP SYN Scan (-sS) |
|---|---|---|
| **Handshake** | Full 3-Way Handshake complete karta hai. | Half-Open (Handshake beech mein tor deta hai). |
| **Privileges** | Kisi bhi normal/unprivileged user sy chal jata hai. | Sirf root ya sudo user hi chala sakta hai (kyunki raw packets banane parte hain). |
| **Logging (Stealth)** | **Less Stealthy.** Application logs mein yeh scan record ho jata hai kyunki connection complete hota hai. | **More Stealthy.** Purane ya simple firewalls aur application logs isay pakar nahi paate kyunki connection kabhi poora banta hi nahi. |
| **Speed** | Thora slow hota hai kyunki OS ko connection manage karna parta hai. | Bohot fast hota hai kyunki yeh raw packets bhej kar foran chora deta hai. |
## 🛠️ Task Terminal Output Ka Analysis
Chalo ab jo terminal output task mein di gayi hai, us ka ek ek hissa dhyan sy dekhte hain:
```text
PORT    STATE SERVICE
21/tcp  open  ftp
22/tcp  open  ssh
53/tcp  open  domain
80/tcp  open  http

```
Nmap ne target machine ko scan kiya aur use total **4 ports** aise mile jo open thay aur listening state mein thay.
Kyunki yeh ek SYN scan tha, is liye in saare **open** ports ne Nmap ko confirm krny ky liye backend par ek ek **SYN-ACK packet** wapis bheja hoga. Jitne ports open hon gy, tumhare AttackBox ko utne hi SYN-ACK packets receive hon gy.
## 📝 Task Questions ky Answers
Upar diye gaye deep analysis ky mutabik yeh hain tumhare exact answers:
### 1. After launching a TCP SYN scan, how many SYN-ACK packets are successfully received in AttackBox?
> **4** *(Kyunki target par 4 ports open hain, aur har open port Nmap ke SYN ke jawab mein ek SYN-ACK packet wapis bhejta hai).*
> 
### 2. How many ports are open on the target machine?
> **4**
> *(Terminal output mein saaf dekh sakte hain: port 21, 22, 53, aur 80 saare open show ho rahe hain).*

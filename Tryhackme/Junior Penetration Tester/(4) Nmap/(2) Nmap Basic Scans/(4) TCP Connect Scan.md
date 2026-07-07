Task 4 par aao! Yeh **TCP Connect Scan (-sT)** ki practical aur deep working samjhata hai.
Chalo pehle isko thora asani sy breakdown karte hain ky backend par kya chal raha hai, aur phir questions ky answers dekhte hain.
## 🔍 TCP Connect Scan (-sT) Kaise Kaam Karta Hai?
Jab tum Nmap par -sT use karte ho, toh yeh target machine ky sath poora **TCP 3-Way Handshake** complete karta hai.
### Case 1: Agar Port Open Ho (Jaise Port 80)
 1. **Nmap** bhejta hai \rightarrow SYN
 2. **Target** jawab deta hai \rightarrow SYN-ACK (Iska matlab port open hai!)
 3. **Nmap** connection complete krny ky liye bhejta hai \rightarrow ACK
 4. Kyunki hum ne sirf check krna tha, data transfer nahi krna, is liye Nmap foran connection tor deta hai by sending \rightarrow RST-ACK (Reset).
### Case 2: Agar Port Closed Ho
 1. **Nmap** bhejta hai \rightarrow SYN
 2. **Target** foran jawab deta hai \rightarrow RST-ACK (Yani yahan koi service nahi hai, dafa ho jao).
> 📌 **Important Point:** Agar tum Linux terminal par root ya sudo user **nahi** ho, toh Nmap default par sirf yahi scan (-sT) run kar sakta hai.
> 
### Useful Extra Options:
 * -F (Fast Mode): Yeh 1000 ports ky bajaye sirf top **100** most common ports scan karta hai (time bachane ky liye).
 * -r (Consecutive Order): Nmap default par ports ko random order mein scan karta hai, lekin -r lagane sy yeh line wise (1, 2, 3...) scan kare ga.
## 📝 Task Questions ky Answers
Jo terminal output task mein di gayi hai, usay dhyan sy dekho. Us mein answers chuppe hain:
```text
PORT    STATE SERVICE
21/tcp  xxxx  ftp
22/tcp  open  ssh
53/tcp  open  xxxxxx
80/tcp  open  http

```
### 1. What is the state of the FTP service running on port 21?
> **xxxx** *(Terminal output mein check karo, 21/tcp ky agay state ke column mein xxxx likha hua hai).*
> 
### 2. What is Nmap’s guess about the service running on port 53?
> **xxxxxx** *(Terminal output mein 53/tcp ky agay service ke column mein xxxxxx likha hai, jo Nmap ka guess ya placeholder show kar raha hai).*
> 

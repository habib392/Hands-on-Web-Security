Task 3 par aao. Yeh task bohot mazeedar hai kyunki ismein hum **TCP Flags** ky baare mein seekhenge. Network security aur port scanning ko master krny ky liye TCP flags ka samajhna sab sy zaroori cheez hai.
Chalo isay bilkul asaan aur short points mein breakdown karte hain.
## 📦 TCP Header aur Flags Kya Hain?
Jab bhi internet par TCP ky zariye koi data jata hai, toh us ky agay ek "header" (packet ka main card) laga hota hai. Iss header mein alag alag informations hoti hain, jaise source port aur destination port.
Iss header ky andar **6 main Flags** (bits) hote hain. Flag set krny ka matlab hai uski value ko 1 (ON) krna. Yeh flags computer aapas mein baat krny ky liye "signals" ky taur par use karte hain:
 * 🔴 **SYN (Synchronize):** Yeh tab use hota hai jab koi connection shuru krna ho (Handshake ka pehla qadam).
 * 🟢 **ACK (Acknowledgement):** Yeh doosray computer ko batata hai ky "Haan, mujhe tumhara packet mil gaya hai."
 * 🟡 **RST (Reset):** Agar koi connection zabardasti ya foran khatm krna ho, ya kisi aisay port par packet jaye jahan koi service na ho, toh computer RST bhejta hai.
 * 🔵 **FIN (Finish):** Jab kaam khatm ho jaye aur connection ko pyaar sy band krna ho.
 * 🟣 **PSH (Push):** Data ko foran application tak bhejne ky liye.
 * 🟠 **URG (Urgent):** Kisi specific data ko priority par process krny ky liye.
## 📝 Task Questions ky Answers
Yahan tumhare questions ky exact answers hain:
### 1. What 3 letters represent the Reset flag?
> **RST**
> 
### 2. Which flag needs to be set when you initiate a TCP connection (first packet of TCP 3-way handshake)?
> **SYN**
> 

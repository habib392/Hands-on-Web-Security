Yeh section **TCP/IP Layers** aur unke protocols ko host discovery (live hosts dhoondne) ke liye explain kar raha hai. Yeh cyber security aur networking ka bohot hi basic aur important concept hai. Aasan Roman Urdu mein iska matlab samajhte hain:
## 🧐 Layers aur Protocols ka Khel (From Bottom to Top)
Jab hum kisi target network par scanning karte hain, to hum alag-alag layers ke protocols ka fayda uthate hain taaki pata chal sake ke kaun si machine online hai:
### 1. Link Layer — ARP (Address Resolution Protocol)
 * **Kaam:** ARP ka sirf ek maqsad hota hai; yeh poore local network segment par ek message broadcast karta hai aur kehta hai: *"Bhai, jis computer ki yeh IP address hai, woh mujhe apna MAC (hardware) address batao."*
 * **Security Context:** Agar device apna MAC address de deti hai, to humein pata chal jata hai ke host **up (online)** hai.
### 2. Network Layer — ICMP (Internet Control Message Protocol)
 * **Kaam:** ICMP ke bohot saare types hote hain, lekin normal ping mein do main types use hoti hain: **Type 8 (Echo Request)** jo hum bhejte hain, aur **Type 0 (Echo Reply)** jo target computer wapas jawab mein bhejta hai.
 * **Important Rule:** Agar aap **same subnet** (apne hi local network) mein kisi system ko ping karenge, to ICMP packet bhejne se pehle aapka system khud-ba-khud aik **ARP query** bhejega taaki us ka MAC address pata chal sake.
### 3. Transport Layer — TCP aur UDP
 * **Kaam:** Halankeh TCP aur UDP data transfer ke liye hote hain, lekin Nmap ya doosre scanners inke packets ko thoda modify (specially craft) karke common ports par bhejte hain yeh check karne ke liye ke target system se koi response aata hai ya nahi.
 * **Bypass Strategy:** Yeh tareeqa tab sabse zyada kaam aata hai jab network par **ICMP Echo (normal ping) block** kiya gaya ho (jaise Cloudflare ya firewalls aksar ping block kar deti hain).

---

## Question/Answers

### Part 1: Computer 1 se Computer 3 ka Scan
Jab aap simulator mein **From: computer1**, **To: computer3**, aur Type **"Ping Request"** select karke send karenge, to yeh same subnet ka scenario hai:
 * **What type of packet did computer1 send before the ping?**
   > **ARP Request**
   > *(Logic: Jaise humne abhi parha, local network par direct IP ping nahi ho sakti jab tak Computer 1 ko Computer 3 ka MAC address na pata ho. Isliye woh pehle ARP Request bhejta hai).*
   > 
 * **What type of packet did computer1 receive before it was able to send the ping?**
   > **ARP Reply**
   > *(Logic: Computer 3 pehle jawab mein apni pehchan (MAC address) bhejega jise ARP Reply kehte hain, tabhi ping packet chalega).*
   > 
 * **How many computers responded to the ping request?**
   > **1**
   > *(Logic: Ping target sirf Computer 3 tha, to sirf usi ne response diya).*
   > 
### Part 2: Computer 2 se Computer 5 ka Scan
Yeh scenario different subnets ka hai, jahan packets ko router aur switch ke zariye guzarna parta hai:
 * **What is the name of the first device that responded to the first ARP Request?**
   > **Router**
   > *(Logic: Chunki Computer 5 doosre network par hai, isliye Computer 2 ko local network se bahar janay ke liye apne Default Gateway yaani Router ka MAC address chahiye hota hai. To pehli ARP request ka jawab Router deta hai).*
   > 
 * **What is the name of the first device that responded to the second ARP Request?**
   > **computer5**
   > *(Logic: Jab packet router ko cross karke target network par jata hai, to router wahan Computer 5 ko dhoondne ke liye doosri ARP request bhejta hai, aur Computer 5 uska reply karta hai).*
   > 
 * **Send another Ping Request. Did it require new ARP Requests? (yea/nay)**
   > **nay**
   > *(Logic: Jab aap dobara ping bhejenge to devices ke paas local cache memory (ARP table) mein aik doosre ka MAC address save ho chuka hota hai, isliye naye ARP requests ki zaroorat nahi parti).*
   > 
In answers ko simulator ke text boxes mein input karein, yeh bilkul correct hain aur aapka yeh task successfully clear ho jayega!


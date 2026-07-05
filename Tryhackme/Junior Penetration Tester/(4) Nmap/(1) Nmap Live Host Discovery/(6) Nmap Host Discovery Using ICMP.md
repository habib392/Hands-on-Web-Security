Yeh section **ICMP (Internet Control Message Protocol) Scans** ko details ke sath samjha raha hai. Jab target aapke local network se bahar ho (yaani router ke par), tab ARP scan kaam nahi karta. Aise mein hum ICMP ke alag-alag packets bhej kar check karte hain ke host online hai ya nahi.
Chalein isko aasan Roman Urdu mein break-down karte hain:
## 🧐 ICMP Scans ki Explanation (3 Main Types)
Cyber security mein normal ping block hona bohot aam baat hai. Isliye Nmap ke paas ICMP ki 3 alag techniques hoti hain:

### 1. ICMP Echo Scan (-PE)
 * **Concept:** Yeh wahi standard ping hai jismein **ICMP Type 8 (Echo Request)** bheja jata hai aur target se **ICMP Type 0 (Echo Reply)** ki umeed ki jati hai.
 * **Problem:** Yeh sabse pehla aur straightforward tareeqa hai, lekin bilkul unreliable hai kyunki Windows ki apni default firewall aur doosri network firewalls standard ping ko foran block kar deti hain.
 * **Scan Result:** Jab simulator mein nmap -PE -sn 10.200.6.0/24 chalaya gaya, to isko **3 hosts up** mile.
### 2. ICMP Timestamp Scan (-PP)
 * **Concept:** Agar normal ping block ho jaye, to Nmap chalaki karta hai. Yeh **ICMP Type 13 (Timestamp Request)** bhejta hai, jismein system ka time pucha jata hai. Target responds with **ICMP Type 14 (Timestamp Reply)**.
 * **Fayda:** Aksar firewalls normal ping to block kar deti hain lekin timestamp request ko check karna bhool jati hain, jis se hum host ka pata laga lete hain.
 * **Scan Result:** Jab terminal par nmap -PP -sn 10.200.6.0/24 chalaya gaya, to sirf **2 hosts up** mile (yaani aik machine ne iska jawab nahi diya/block kar diya).
### 3. ICMP Address Mask Scan (-PM)
 * **Concept:** Yeh teesra rasta hai jahan Nmap **ICMP Type 17 (Address Mask Query)** bhej kar subnet mask ki maloomat maangta hai aur **ICMP Type 18 (Address Mask Reply)** ka wait karta hai.
 * **Scan Result:** Jab text mein nmap -PM -sn 10.200.6.0/24 chalaya gaya, to **0 hosts up** ka result aaya.
 * **Sabak:** Iska matlab yeh nahi ke hosts offline hain, balki raste mein kisi firewall ya target operating system ne is specific ICMP type ko poori tarah block kar diya hai. Isliye aik penetration tester ko saare options ka pata hona chahiye.

---

## 🎯 Questions & Answers
Aap se is task ke aakhir mein Nmap ke flags (options) ke baare mein pucha gaya hai. Inke answers bilkul seedhe hain:
 * **Question 1:** What is the option required to tell Nmap to use ICMP Timestamp to discover live hosts?
   > **-PP**
   > 
 * **Question 2:** What is the option required to tell Nmap to use ICMP Address Mask to discover live hosts?
   > **-PM**
   > 
 * **Question 3:** What is the option required to tell Nmap to use ICMP Echo to discover live hosts?
   > **-PE**
   > 
*(Tip: In flags ko hamesha capital letters mein -PP, -PM, aur -PE ki tarah hi text boxes mein enter kijiyega).*

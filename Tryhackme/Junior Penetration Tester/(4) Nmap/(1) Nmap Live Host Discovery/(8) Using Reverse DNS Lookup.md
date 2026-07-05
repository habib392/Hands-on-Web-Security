Yeh section **Reverse DNS (rDNS)** ke bohot hi useful concept ko samjha raha hai. Reconnaissance aur information gathering mein yeh bohot kaam aata hai. Chalein isko aasan Roman Urdu mein break-down karte hain:

## 🧐 Reverse DNS (rDNS) Kya Hai?
Normal DNS mein hum Nmap ko domain name dete hain aur woh IP address dhoondta hai (jaise: nineforbrands.com.au \rightarrow IP). **Reverse DNS iska bilkul ulta hai.** Isme hum Nmap ko IP address dete hain aur poochte hain ke *"Is IP par kaun sa domain name ya hostname chal raha hai?"* (jaise: 10.200.6.15 \rightarrow mail.company.local).
### 🛡️ Cyber Security mein iska Fayda:
 * **System Roles ka Pata Chalna:** Agar aap kisi network par scan kar rahe hain aur rDNS se kisi IP ka naam dc01.domain.com ya backup-server.local nikal aata hai, to aapko foran pata chal jata hai ke yeh **Domain Controller** ya **Backup Server** hai. Phir aap uske mutabiq targeted attack ya testing kar sakte hain.
 * **Nmap ke Flags:**
   * **-R**: Yeh Nmap ko majboor (force) karta hai ke woh **saare** hosts (chahe woh online milen ya offline) ka Reverse DNS lookup zaroori kare.
   * **-n**: Yeh Reverse DNS lookup ko bilkul **band (disable)** kar deta hai. (Humne pichli commands mein iska use kiya tha taaki scan tez ho jaye aur Nmap DNS queries par time zaya na kare).
   * **--dns-servers**: Agar aap kisi specific DNS server (jaise company ke internal DNS) se pooch-gach karna chahte hain, to aap yeh option use karte hain.

---

## 🎯 Question & Answer
Aap se is section ke aakhir mein aik seedha sawaal pucha gaya hai:
**Question:** We want Nmap to issue a reverse DNS lookup for all the possible hosts on a subnet, hoping to get some insights from the names. What option should we add?
 * **Answer:** **-R**
*(Logic: Text mein saaf bataya gaya hai ke by default Nmap sirf online hosts ko check karta hai, lekin agar aap saare possible hosts ka lookup force karna chahte hain to **-R** ka flag use hota hai).*

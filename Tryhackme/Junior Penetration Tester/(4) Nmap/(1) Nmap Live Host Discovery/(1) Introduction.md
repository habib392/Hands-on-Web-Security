Yeh TryHackMe ke **Nmap Live Host Discovery** room ka introduction aur learning objectives hain. Chalain isko aasan Roman Urdu mein samajhte hain ke yeh room aapko kya sikhana chaah raha hai aur cyber security mein iski kya ahmiyat hai.

## 🧐 Room ki Explanation: Nmap Kya Hai?
Yeh section batata hai ke **Nmap (Network Mapper)** ek bilkul free aur open-source tool hai jise Gordon Lyon (Fyodor) ne banaya tha. Yeh pooray cyber security aur networking ki industry ka sabse standard tool hai jiske 3 main kaam hain:
 1. **Mapping Networks:** Network ka poora naksha nikalna.
 2. **Identifying Live Hosts:** Yeh pata lagana ke kaun kaun se computers ya servers online (up) hain.
 3. **Discovering Services:** Un servers par kaun si services (jaise web server, database, SSH) chal rahi hain.
Iske paas ek **NSE (Nmap Scripting Engine)** bhi hota hai, jiski madad se aap advanced kaam kar sakte hain, jaise vulnerabilities ka pata lagana ya unhein exploit karna.
## 🎯 Learning Objectives (Aap Is Room Se Kya Seekhenge?)
Jab hum kisi network ya website par testing shuru karte hain, to hamare paas do main sawaal hote hain:
 1. **Kaun se systems online/alive hain?** (Iska jawaab aapko isi room mein milega).
 2. **Un par kaun si services chal rahi hain?** (Iska jawaab agle rooms mein milega jo port scanning par hain).
Is room ke main topics yeh hain:
 * **Host Discovery Kyun Zaroori Hai?:** Port scanning se pehle host discovery karna kyun zaroori hai? Agar ek system pehle se offline (down) hai aur aap us par aggressive scanning shuru kar dein, to aapka time bhi zaya hoga aur network par fazool ka noise (traffic) paida hoga jis se firewall aap ko pakar legi.
 * **ARP Scans (Link Layer):** Jab aap local network (same subnet) mein hote hain, to ARP scan broadcast requests bhej kar live hosts ko bohot jaldi aur accurately dhoond leta hai.
 * **ICMP Scans (Network Layer):** Jab target kisi doosre network segment par ho, to ICMP Echo (ping), Timestamp, aur Address Mask requests ka use karke live hosts ka pata lagaya jata hai.
 * **TCP SYN & ACK Ping Scans (Transport Layer):** Yeh bohot important hai. Isme transport layer ke packets bhej kar check kiya jata hai ke host online hai ya nahi. Saath hi aap seekhenge ke **Privileged (Root/Sudo user)** aur **Unprivileged (Normal user)** scan ke behaviour mein kya farq hota hai.
 * **UDP Ping Scans:** Agar TCP block ho, to UDP packets bhej kar target ke closed ports se *ICMP port-unreachable* ka response trigger kiya jata hai, jis se confirm ho jata hai ke host online hai.

## 1. Traceroute Kya Hai?
Jab aap apne computer se kisi website (jaise facebook.com ya TryHackMe ke server) par jaate ho, toh aap ka data direct wahan nahi pahunchta. Woh raste mein bohot saare routers se guzar kar jata hai, jinhein hum **Hops** kehte hain.
 * **Traceroute ka Kaam:** Yeh aap ko batata hai ke aap ka data target tak pahunchne ke liye **kaun kaun se routers** se guzar raha hai aur un routers ke IP addresses kya hain.
 * **Commands:** Linux par yeh command traceroute MACHINE_IP hoti hai aur Windows par yeh tracert MACHINE_IP hoti hai.
## 2. Traceroute Kaam Kaise Karta Hai? (The Hacker's Trick)
Internet par aisa koi direct rule nahi hai jo aap ko raste ke saare routers ka naam bata sake. Iss liye traceroute aik bohot hi chalaki wala tareeqa use karta hai: **Yeh TTL ko 1 se shuru karta hai!**
### Step-by-Step Samjho:
 1. **Pehla Packet (TTL = 1):** Traceroute pehla packet bhejta hai aur us par TTL ki value 1 set kar deta hai. Packet jaise hi aap ke ghar ke pehle router (Modem) par pahunchta hai, router us mein se 1 minus karta hai, toh TTL ho jata hai **0**. Router packet ko drop kar deta hai aur aap ko ICMP message bhejta hai: *"Bhai, Time Exceeded (TTL khatam)"*. **Traceroute ko pehle router ka IP mil gaya!**
 2. **Doosra Packet (TTL = 2):** Ab traceroute doosra packet bhejta hai jis par TTL 2 hota hai. Yeh pehle router se guzar jata hai (wahan TTL 1 ho jata hai) aur jaise hi doosre router par jata hai, TTL **0** ho jata hai. Doosra router packet drop karta hai aur ICMP reply bhejta hai. **Traceroute ko doosre router ka IP bhi mil gaya!**
 3. **Yeh chalta rehta hai (TTL = 3, 4, 5...):** Yeh tab tak chalta rehta hai jab tak packet aakhir kaar target server tak nahi pahunch jata.
Is tarah, aik aik kar ke raste ke saare routers khud hi apna IP address hacker ko bata dete hain!
## 3. Aik Zaroori Baat: Rasta Badalta Rehta Hai
Traceroute parhte waqt yeh yaad rakhna ke internet par packets ka rasta fix nahi hota.
 * Routers **BGP** ya **OSPF** jaise dynamic protocols use karte hain. Iska matlab hai agar raste mein koi aik router busy hai ya down hai, toh agla packet automatic doosre raste se nikal jayega.
 * Is liye agar tum aik hi website par do baar traceroute chalao, toh ho sakta hai dono baar raste ke routers thore mukhtalif (different) nazar aayein.
### Summary in Short:
Traceroute aik asalaah (tool) hai jo **TTL ko barha barha kar** (1, 2, 3...) raste ke routers ko jaan boojh kar forced karta hai ke woh packet drop karein aur apna IP address bheinjein.

---

## 1. Output ko Kaise Parhte Hain? (Reading the Output)
Traceroute jab chalta hai, toh har line aik **Hop** (router) ko represent karti hai.
 * **3 Packets Per Line:** Traceroute har TTL value par **3 packets** bhejta hai. Iss liye aap ko har line mein **3 IP addresses** aur **3 round-trip times (ms)** nazar aate hain.
 * **Churriyaan * (Asterisk) ka Matlab:** Agar kisi line mein * * * ya koi aik * nazar aaye, toh iska matlab hai ke us router ne ya toh packet drop kar diya, ya us ki firewall ne ICMP message bhejna block kiya hua hai (**Filtered/Suppressed**). Secure environments mein aisa jaan booch kar kiya jata hai taake hacker naksha na bana sake.
 * **Aakhri Line:** Jo sab se aakhri line hoti hai (jaise Traceroute A mein Hop 14 aur Traceroute B mein Hop 26), woh aap ka asli **Target Server** hota hai. Jab target mil jata hai, traceroute ruk jata hai.
## 2. Traceroute A vs Traceroute B: Itna Bara Farq Kyun?
Agar tum ghaur karo, toh tryhackme.com par pehli baar traceroute chalaya toh **14 hops** mein target mil gaya. Lekin doosri baar chalane par **26 hops** lage!
### Aisa Kyun Hua?
 1. **Load Balancing & Anycast:** tryhackme.com Cloudflare (CDN) use karta hai. Cloudflare ke servers poori duniya mein hain. Jab network par traffic badhta hai ya koi router busy hota hai, toh load balancers packets ka rasta badal dete hain taake website fast load ho.
 2. **Dynamic Routing:** Internet par rasta badalta rehta hai. Ho sakta hai pehli run mein short cut mila ho, aur doosri run mein data lamba chakkar kaat kar gaya ho.
## 3. Advanced Traceroute Techniques (Hacker's Choice)
Aam tor par Linux par traceroute **UDP packets** bhejta hai. Lekin modern firewalls UDP ko block kar deti hain. Iss liye aap ke paas do advanced tareeqe hain firewalls ko bypass karne ke:
 * **TCP Mode (traceroute -T MACHINE_IP):** Yeh UDP ke bajaye TCP packets bhejta hai. Kyunke websites TCP port 80/443 par chalti hain, firewalls aksar lagti hain ke yeh aam web traffic hai aur isko allow kar deti hain.
 * **ICMP Mode (traceroute -I MACHINE_IP):** Yeh plain ping (ICMP Echo Requests) use karta hai rasta nikalne ke liye.
### 🛠️ MTR (My Traceroute) — mtr MACHINE_IP
Traceroute chala kar ruk jata hai, lekin mtr aik aisa tool hai jo **Traceroute aur Ping dono ko mila deta hai**. Yeh real-time mein chalta rehta hai aur aap ko live batata hai ke raste ke kis router par kitna packet loss ho raha hai aur latency kitni hai.

---

Tum **Traceroute** ko aam tor par do baday kaamon ke liye use karoge:
## 1. Information Gathering aur Network Mapping (Reconnaissance)
Cyber security mein attack karne se pehle target ke baare mein maloomat jama ki jati hain, jise hum **Recon** kehte hain.
 * **Faida:** Traceroute se tumhein pata chal jata hai ke target company ka network infrastructure kaisa hai. Raste ke aakhri kuch routers aam tor par us company ke apne hote hain.
 * **Firewall ka pata lagana:** Agar hop 10 tak IP addresses show ho rahe hain aur us ke baad sirf * * * aa raha hai, toh tum samajh jaate ho ke hop 10 ke foran baad company ki **Firewall** ya **IDS (Intrusion Detection System)** baithi hai jo traffic ko rok rahi hai.
 * **Internal Network ka andaza:** Kabhi kabhi routers ke naam (DNS names) se un ki location ya kaam ka pata chal jata hai (jaise uk-router.target.com ya fw-core.target.com). Is se hacker ko samajh aa jata hai ke target network ka dacha (topology) kaisa hai.
## 2. Network Troubleshooting (Raste ki Rukawat Dhundna)
Socho tum kisi company mein security analyst ho aur wahan ka aik server achanak down ho jata hai ya bohot slow ho jata hai. Ab tum ping karte ho toh response nahi aata.
 * **Faida:** ping tumhein sirf yeh bataye ga ke "bhai, server tak nahi pahunch pa rha". Lekin traceroute tumhein **asli jagah** bataye ga jahan masla hai.
 * Agar traceroute hop number 5 tak bilkul sahi gaya aur hop 6 par ja kar atak gaya, toh iska matlab hai ke tumhara internet ya target server kharab nahi hai, balki **hop number 5 aur 6 ke darmiyan jo router hai, masla wahan hai!** Woh router down ho sakta hai ya wahan bohot zyada traffic congestion (latency) ho sakti hai.
### 📝 Aik Choti si Summary
| Scenario | Tum Traceroute Kyun Chalao Ge? |
|---|---|
| **As a Hacker / Pen Tester:** | Taake target network ka naksha (map) banaya ja sake aur dekha jaye ke raste mein kahan kahan firewalls lagi hain. |
| **As a Network Defender:** | Taake network mein latency (slow internet) ya disconnection ka point dhoonda ja sake ke data kis router par ja kar phas raha hai. |

Yeh section **Transport Layer (TCP aur UDP) Ping Scans** ko bohot detail mein explain kar raha hai. Jab network par ICMP (normal ping) ko block kiya gaya ho, to Nmap transport layer ke packets ka use karta hai taaki firewalls ko chakma de sake.
Chalein is pure text ko aasan Roman Urdu mein break-down karte hain:

## 🧐 Transport Layer Scans ki Explanation
### 1. TCP SYN Ping (-PS)
 * **Logic:** Nmap target ke port 80 (default) par ek SYN packet bhejta hai.
   * Agar port **open** hoga, to target wapas **SYN/ACK** bheje ga.
   * Agar port **closed** hoga, to target **RST (Reset)** packet bheje ga.
 * **Jackpot Rule:** Humain port ke open ya closed hone se farq nahi parta; agar target se SYN/ACK ya RST mein se koi bhi response aata hai, to iska matlab hai ke **host online hai**!
 * **Privilege Farq:**
   * **Privileged User (sudo):** Yeh raw packets bhejta hai aur open port se SYN/ACK aane par handshake complete nahi karta (RST bhej kar transaction wahin tor deta hai), jo ke fast aur stealthy hota hai.
   * **Unprivileged User:** Iske paas raw socket ka ikhtiyar nahi hota, isliye yeh majbooran poora TCP 3-way handshake complete karta hai.
### 2. TCP ACK Ping (-PA)
 * **Logic:** Nmap direct target par **ACK** packet bhejta hai.
 * **Reaction:** Chunki target ke paas is packet se pehle koi connection chal nahi raha hota, to target ka operating system confuse ho kar foran jawab mein **RST (Reset)** packet bhejta hai. Jab RST aata hai, to Nmap samajh jata hai ke host live hai.
 * **Strict Rule:** Yeh scan chalane ke liye aapka **Privileged User (sudo)** hona zaroori hai. Agar normal user chalaye ga, to Nmap majbooran isko SYN scan (3-way handshake) mein convert kar dega.
### 3. UDP Ping (-PU)
 * **Logic:** TCP ke ulta, agar aap UDP packet kisi open port par bhejenge to aksar koi jawab nahi aata. Isliye Nmap jaan bujh kar ek **ajeeb aur closed UDP port** par packet bhejta hai.
 * **Reaction:** Jab packet closed UDP port par jata hai, to target system majbooran **ICMP Port-Unreachable** ka error message generate karta hai. Jaise hi Nmap ko yeh error milta hai, use pata chal jata hai ke machine active hai.

---

## 🎯 Questions & Answers
Is task ke aakhir mein puche gaye sawalaat ke sahi answers yeh hain:
 * **Question 1:** Which TCP ping scan does not require a privileged account?
   > **TCP SYN Ping**
   > *(Logic: Text mein clear bataya gaya hai ke unprivileged users ke paas koi aur option nahi hota siwaye SYN ping ke zariye 3-way handshake complete karne ke).*
   > 
 * **Question 2:** Which TCP ping scan requires a privileged account?
   > **TCP ACK Ping**
   > *(Logic: ACK ping chalane ke liye explicitely privileged/root account hona zaroori hai).*
   > 
 * **Question 3:** What option do you need to add to Nmap to run a TCP SYN ping scan on the telnet port?
   > **-PS23**
   > *(Logic: TCP SYN ping ka flag -PS hota hai aur Telnet ka standard port number **23** hota hai. Dono ko mila kar -PS23 banega).*
   > 
In answers ko enter karein, aapka yeh section bhi clear ho jaye ga! Next task par chalien?

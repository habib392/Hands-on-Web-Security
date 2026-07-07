Ab iss room ky aakhri task yani **Task 8: Summary** ka poora nichor (wrap-up) nikalte hain. Yeh poore room ka ek quick aur bohot hi zabardast revision sheet hai, jo tumhein hamesha yaad rakhni hai.
Chalo is poori summary ko aik dafa dhyan sy samajhte hain taakay aglay advanced room mein janay sy pehle saare basics bilkul pkay hon.

## 📊 Summary Table 1: Main Port Scans
Hum ne teen main scans parhay, unka purpose aur unki commands ka farq yeh hai:
| Scan Type | Purpose / Feature | Example Command |
|---|---|---|
| **TCP Connect Scan** | Poora 3-Way Handshake mukammal karta hai. Unprivileged (normal user) ky liye yahi option hota hai. | nmap -sT MACHINE_IP |
| **TCP SYN Scan** | Half-Open / Stealth Scan hai. Connection poora nahi karta (RST bhej deta hai). sudo zaroori hai. | sudo nmap -sS MACHINE_IP |
| **UDP Scan** | Connectionless ports (jaise DNS) ko check karta hai. ICMP Port Unreachable error par closed batata hai. | sudo nmap -sU MACHINE_IP |
## 🛠️ Summary Table 2: Customization Flags
Scan ki speed, ports ki range, aur performance ko fine-tune krny ky liye yeh switches bohot kaam aate hain:
 * **-p-** : Saare 65,535 ports ko scan krny ky liye.
 * **-p1-1023** : Sirf standard 1 sy lekar 1023 tak ky ports scan krny ky liye.
 * **-F** : Fast mode, jo sirf top 100 most common ports check karta hai.
 * **-r** : Ports ko line-wise (consecutive order) mein scan karta hai, random nahi.
 * **-T<0-5>** : Speed templates. -T0 sab sy slow aur paranoid (stealthy) hai, jab ky -T5 sab sy tezi (insane) hai jo target crash bhi kar sakti hai. Default -T3 hota hai.
 * **--max-rate 50** : Ek second mein 50 packets sy zyada nahi bheje ga (firewall sy bachne ky liye).
 * **--min-parallelism 100** : Kam sy kam 100 probes (packets) ek sath parallel mein active rakhe ga speed barhane ky liye.

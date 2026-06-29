## Active vs. Passive Reconnaissance: Farq Kya Hai?
Pehle tum ne **Passive Reconnaissance** parha tha. Dono mein simple farq yeh hai:
 * **Passive Reconnaissance:** Iss mein aap target ki website ya server ko touch nahi krte. Aap publically available data use krte hain (jaise DNS records, WHOIS, ya Shodan). Target ko pata hi nahi chalta ke koi uss ke baare mein info nikal raha hai.
 * **Active Reconnaissance:** Iss mein aap **direct target ke sath interact** krte hain. Aap uss ke server par packets bhejte hain, connections banate hain, aur check krte hain ke kaun si services chal rahi hain.
## ⚠️ Sab se Badi Baat: Traces (Nishan-dehi)
Kyunke aap direct target ke ghar ka darwaza khatkhatate hain (packets bhejte hain), is liye aap ke piche **traces** (saboot) reh jaate hain. Target ke security systems aap ko pakar sakte hain:
 * **Log Entries:** Server ke records mein aap ka IP address save ho jata hai.
 * **IDS Alerts (Intrusion Detection System):** Yeh system alert generate kr deta hai ke koi abnormal activity ho rahi hai.
 * **WAF Blocks (Web Application Firewall):** Agar firewall ko lagay ke aap attack ya scan kr rahe hain, toh woh aap ko block kr dega.
 * **Honeypot Triggers:** Honeypots fake systems hote hain jo hackers ko phasane ke liye banaye jaate hain. Agar aap unhein touch krenge toh alert chal jayega.
## Iss Room Mein Aap Kya Seekhenge?
Ab tak aap ne chup kar kaam kiya, lekin iss room mein aap **front foot par aakar direct engagement** krenge. Aap mukhtalif tools use kr ke target se woh information nikalwayenge jo passive tareeqon se nahi mil sakti thi.
### Tools Jo Aap Use Krenge:
 1. **Web Browsers:** Website ko manually check krna.
 2. **Ping:** Yeh check krne ke liye ke target system online (alive) hai ya nahi.
 3. **Traceroute:** Yeh dekhne ke liye ke aap ka data target tak pahunchne mein raste mein kaun kaun se routers se guzar raha hai.
 4. **Telnet & Netcat (nc):** Target ke specific ports aur services ke sath connect ho kar un se baat krne aur banner grabbing (version info nikalne) ke liye.
Portswigger ki vulnerabilities solve krte waqt bhi jab aap burp suite se request bhejte ho, toh woh bhi aik tarah se active interaction hi hoti hai.

---

## 1. Prerequisites (Pehle se kya aana chahiye?)
Room kehta hai ke aap ko basic networking ka pata hona chahiye, jaise:
 * **TCP / UDP / ICMP** protocols kya hain.
 * **Port Numbers** kya hote hain.

## 2. Aaj Kal ke Daur Mein Active Recon Mushkil Kyun Hai?
Pehle zamane mein scanning aasan thi, lekin **2026 ke modern daur mein** companies bohot active hain:
 * **CDNs (Cloudflare / Akamai):** Yeh website ke aage dhaal ban kar khari hoti hain aur unusual traffic ko foran block kar deti hain.
 * **IPv6:** Aaj kal bohot se servers purane ping ka jawab nahi dete, balkay ping6 use krte hain.
 * **SIEM aur EDR Systems:** Yeh advanced defensive tools hain jo kisi bhi kism ki scanning pattern ko seconds mein detect kar lete hain.

## 3. Telnet Kyun Parh rahe hain jab yeh purana ho chuka hai?
Aap sochoge ke jab **Telnet** unencrypted (unsafe) hai aur koi use nahi karta, toh hum kyun seekh rahe hain?
 * **Fundamentals:** Yeh samajhne ke liye ke **Banner Grabbing** (server ka version pata karna) kaise hoti hai.
 * **Legacy Systems:** Aaj bhi bohot si purani companies ya sarkari idaron ke systems purani technology use kar rahe hote hain, jahan telnet mil jata hai aur woh asani se hack ho sakte hain.

## 4. 🚨 Sab se Important Rule: Legal Authorization
> **"Never perform active reconnaissance without explicit, signed legal authorisation."**
> 
Cyber security mein sab se badi boundary yahi hai. Kisi bhi website ya server par bina ijazat (Penetration Testing Contract ya Bug Bounty Scope ke baghair) active scanning karna **illegal (jurm)** hai. Hamesha apni labs ya authorized targets par hi practice karni hai.

## 5. Red Team vs. Blue Team Perspective
 * **Red Team (Attacker):** In ka maqsad hota hai ke woh aam traffic mein **blend in** (chup) jayein. Jaise agar aap browser se normal website visit karoge, toh firewall ko lagega ke koi aam user hai.
 * **Blue Team (Defender):** Yeh log logs aur alerts ko monitor karte hain taake attacker ko shuru mein hi pakar lein.
## 🎯 Learning Objectives (Aap Kya Seekhenge?)

Iss room ko complete karne ke baad aap in cheezon ke ustad ban jayenge:
 1. **Web Browser DevTools:** JavaScript files, headers, aur certificates se khufia info nikalna.
 2. **Ping:** Target online hai ya nahi, aur **TTL (Time to Live)** value se yeh andaza lagana ke target Windows hai ya Linux.
 3. **Traceroute & MTR:** Raste ke routers ka map banana.
 4. **Telnet & Netcat (nc):** Ports check karna aur banner grabbing karna.
> 💡 **Tip:** Yeh room **Nmap** (jo ke scanning ka king tool hai) seekhne se pehle ka pehla qadam hai.
> 
## ⚠️ Important Note for TryHackMe
Agar aap TryHackMe ka free version use kar rahe hain, toh in-browser AttackBox se direct internet access nahi milegi. Iss ke liye aap ko apne computer par **OpenVPN** connect karna hoga taake labs sahi se kaam karein.

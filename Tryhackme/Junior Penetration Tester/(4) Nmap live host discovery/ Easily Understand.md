## 🎯 Asal Maqsad Kya Hai?
Aap ek hacker ya penetration tester hain. Aapko ek company ka network de diya gaya (farz karein unka network range 10.200.6.0/24 hai, jismein **254** IPs ho sakti hain).
Aapka sabse pehla kaam yeh hai ke yeh pata lagana ke **in 254 computers mein se kaun se computers asal mein chal rahe (online) hain?**
Kyunki jo computer band hai, us par port scan chalana ya attack karna apna time zaya karna hai.


## 🤔 To Phir Itni Saari Commands Aur Tareeqay Kyun Hain?
Aap soch rahe honge ke *"Bhai, simple computer ko ping karo, agar jawab aaye to online hai, nahi to offline hai! Baat khatam!"*

Asal zindagi mein aisa nahi hota. Yahan aati hai **Firewall**.
Har company ne security lagayi hoti hai. Agar aap aik tareeqay se check karenge, to firewall aapko block kar degi. Isliye Nmap ke paas yeh alag-alag chabiyaan (commands) hain:

### 1. Simple Ping (-PE) — Pehli Chabi
Aapne normal ping kiya. Agar target Windows 10 ya Windows 11 hai, to uski default firewall is ping ko block kar degi. Nmap kahega "Host is down" (halankeh computer chal raha hai). Aap nakaam ho gaye.

### 2. ICMP Timestamp (-PP) — Doosri Chabi
Aapne dimaag chalaya. Aapne kaha, "Acha, normal ping block hai? Main is system se time poochta hoon." Aapne -PP chalaya. Firewall ne socha yeh to sirf time pooch raha hai, usne packet guzarne diya. Computer ne apna system time bhej diya. Aapko pata chal gaya ke **computer online hai!** Firewall bypass ho gayi.

### 3. TCP SYN Ping (-PS) — Teesri Chabi
Farz karein firewall bohot strict hai, usne saare ICMP (ping) packets block kiye hue hain. Ab aap kya karenge?
Aap networking ka fayda uthayenge. Aap us computer ke port 80 (website port) par ek aadha-adhura connection request (SYN) bhejenge. Computer chal raha hoga to woh bholepan mein jawab mein SYN/ACK ya RST packet wapas bhejega. Jaise hi Nmap ko woh packet mila, aap samajh gaye ke **bhai machine zinda hai!**

### 4. UDP Ping (-PU) — Chauthi Chabi
Agar usne TCP bhi block kiya hua hai, to aap UDP packet bhejte hain kisi aisi jagah jahan koi kaam na ho raha ho. Computer majbooran cheekh uthta hai: *"Port Unreachable!"* (Bhai yahan koi nahi hai). Uske cheekhne se aapko pata chal gaya ke computer on hai.

## 💡 Baat Ka Nichor (TL;DR)
Yeh saari commands sirf aur sirf **aik hi kaam** karne ke liye hain: **"System on hai ya off?"**
 * Hum alag-alag commands isliye seekh rahe hain kyunki agar real life mein target par **Option A** block ho, to hum **Option B** use karein. Agar **Option B** block ho, to **Option C** use karein.
Yeh saari commands ratti hui yaad rakhne ki zaroorat bilkul nahi hai! Real life mein hum zyadatar sirf nmap -sn <target> chalate hain, aur Nmap itna samajhdar hai ke woh khud hi background mein teen chaar tareeqay mix karke check kar leta hai.

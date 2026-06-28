### Passive vs Active Reconnaissance: Farq Kya Hai?
 * **Passive Reconnaissance:** Iska matlab hai target (website ya server) ko bina touch kiye, bina us par koi traffic bhejay, bahaar bahaar sy publicly available information nikalna. Yeh bilkul aisy hi hai jaisy kisi ghar mein chori krny sy pehly chor sirf bahaar sy khra hokar dekhay ky ghar ka rang kaisa hai ya bahaar kya likha hai. Target ko pata hi nahi chalta ky koi us par nazar rakh rha hai.
 * **Active Reconnaissance:** Is mein hum direct target sy interact krty hain (jaisy ping krna ya nmap scan chalana). Is mein pakray jany (firewall ya IDS mein detect hony) ka risk hota hai.
### Hum Is Room Mein Kya Seekhein Gy?
Is room ky main tools aur objectives yeh hain, jinhein hum agy barh kr aik aik kr ky detail mein parhein gy:
 1. **WHOIS Query:** Kisi domain ki registration details (kis ky naam par hai, kab register hua, email waghaira) nikalna.
 2. **DNS Queries (dig & nslookup):** Domain Name System sy records (IP address, mail servers, text records) nikalna.
 3. **Subdomain Discovery:** DNSDumpster aur Certificate Transparency (crt.sh) logs ky zariye aisy subdomains dhoondna jo aam tor par nazar nahi aaty.
 4. **Shodan.io:** Internet pr connected devices aur exposed services ka data dhoondna.
### 💡 Ek Zaroori Baat (Prerequisites & Connection)
 * **Internet Access:** Jaisa ky notice mein likha hai, agar tum in-browser AttackBox use kr rhy ho aur woh subscription ky bina hai, toh us mein direct internet nahi hoga. Is liye **OpenVPN** ky zariye apny local Kali Linux (ya jo bhi OS tum use kr rhy ho) ko TryHackMe sy connect kr lena taakay tum DNSDumpster aur Shodan jaisi websites ko browse kr sako.
 * **No Deployment Needed:** Is room mein koi machine start krny ki zaroorat nahi hai, sab kaam public internet data aur commands sy hoga..

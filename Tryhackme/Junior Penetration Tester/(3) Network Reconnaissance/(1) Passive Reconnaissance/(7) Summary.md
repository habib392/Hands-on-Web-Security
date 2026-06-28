Yeh is room ka **Conclusion (Summary)** aur aik behtareen **Cheat Sheet** hai. Isko apnay paas save kar lo kyun ky future mein jab tum Bugcrowd ya kisi bhi platform par real-world bug bounty karo gy, toh yeh saari commands tumharay boht kaam aayein gi.
Chalo is pooray room ka aik quick recap kr lein taakay sab kuch bilkul pakka ho jaye:
### 🔑 Key Takeaways (Jo Humne Seekha)
 1. **Passive Recon ka Faida:** Koi alert trigger nahi hota, target ko pata nahi chalta, aur legal risk zero hota hai kyun ky hum saara data public sources sy letay hain.
 2. **WHOIS / RDAP:** Domain kis ny aur kab register kiya, uski dates aur registrar ka pata lagana.
 3. **DNS Queries (dig):** Recommended tool dig hai kyun ky yeh TTL dikhata hai aur clean output deta hai. Is sy hum A (IP), MX (Mail), aur TXT records nikalte hain.
 4. **Subdomain Discovery (crt.sh):** Certificate Transparency logs sab sy best tareeqa hain hidden subdomains dhoondnay ka.
 5. **Shodan.io:** Internet par connected devices aur unky open ports/banners ko search krna.
### 💻 Quick Command Reference Table
| Purpose | Command |
|---|---|
| **WHOIS Lookup** | whois tryhackme.com |
| **DNS A Record (IPv4)** | dig tryhackme.com A |
| **DNS MX Record (Mail)** | dig @1.1.1.1 tryhackme.com MX |
| **DNS TXT Record** | dig tryhackme.com TXT |
| **Subdomain Wildcard** | Visit crt.sh and search %.tryhackme.com |
### 💡 Last Expert Tip
Internet par data badalta rehta hai—IPs change hoti hain, naye subdomains aate hain. Is liye hamesha fresh recon kiya karo jab bhi naya target shuru karo.

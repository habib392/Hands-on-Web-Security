Yeh task boht hi mazaidaar hai kyun ky yahan sy real-world bug bounty aur penetration testing ki jaan shuru hoti hai, jisay hum **Subdomain Discovery** kehty hain.
Aam tor par jab hum dig ya nslookup krty hain, toh humein sirf main domain (jaisy tryhackme.com) ka pata chalta hai. Lekin companies ky boht sy khufia ya bhoolay huay subdomains hoty hain (jaisy dev.tryhackme.com ya admin.tryhackme.com). In subdomains par aksar purani ya kamzor security wali websites chal rhi hoti hain, jinhein hackers target krty hain.
Is task mein do behtareen passive tareeqay bataye gaye hain:

## 1. DNSDumpster
Yeh aik free OSINT website hai jo bina target ko touch kiye (fully passive) boht saara public DNS data jama kr ky dikhati hai.
 * Yeh search engines, certificate records, aur baqi jagahon sy data dhoondti hai.
 * Is mein subdomains ki list, unky IP addresses, geolocation, aur aik behtareen **visual graph (map)** milta hai jo dikhata hai ky kaun sa domain kis IP sy jura hua hai.

## 2. Certificate Transparency (CT) Logs (crt.sh)
Yeh aaj kal ka **sab sy powerful** passive subdomain discovery ka tareeqa hai.
 * **Concept:** 2015 sy yeh rule lazmi hai ky jab bhi koi website secure (HTTPS/SSL certificate) banaye gi, toh us certificate ka record aik public log mein save hoga.

 * **Hacker Trick:** Hum **[https://crt.sh](https://crt.sh)** par ja kar agar % .target.com (% yani wildcard) search krein, toh aaj tak us company ny jitni bhi subdomains ky liye certificates liye hoty hain, un sab ki list samnay aa jati hai. Yeh bilkul passive hai aur is sy sab sy zyada hidden subdomains miltay hain.

## 🎯 Question Solution
Sawaal mein pucha gaya hai:
> **Lookup tryhackme.com on DNSDumpster. Under Services / Banners, which one has the highest count?**
> 
### Answer nikalne ka tareeqa:
 1. Apne browser mein **dnsdumpster.com** open karo.
 2. Search bar mein **tryhackme.com** likh kar search karo.
 3. Thoda sa scroll down karo, wahan aik section hoga jiska naam hoga **"Services / Banners"** ya **"Server Banners"**.
 4. Wahan different servers ky naam (jaisy Apache, Cloudflare, NGINX waghaira) likhay hon gy aur unky sath unka count (number) likha hoga.
Chunkay TryHackMe apny saaray domains aur traffic ky liye Cloudflare use krta hai, toh wahan sab sy bada count **Cloudflare** ka hi hoga.

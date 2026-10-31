# WEB ARCHITECTURE & PENETRATION TESTING MASTER NOTES
## 1. Domain & Hosting
 * **Domain Name (e.g., khan.com):** Yeh koi computer ya hardware nahi hai. Yeh sirf ek human-readable address/name tag hai jo DNS ke zariye server ke IP address (e.g., 192.168.1.1) par route karta hai.
 * **Hosting:** Apni website ki files aur database ko 24/7 chalne wale aur high-speed internet se connected computer (Server) par rakhna aur us storage/resources ka rent dena **Hosting** kehlata hai.
 * **Data Center:** Hosting companies ke wo bare air-conditioned kamre jahan hazaaron physical servers rakhe hote hain.
## 2. Server vs. Database (The Key Difference)
| Component | Role & Functionality | Storage & Contents |
|---|---|---|
| **Server** | Hardware (CPU, RAM) + Operating System (Linux/Windows) + Web Server Software (Apache/Nginx). All actions, logic, calculations, file uploads, permissions, and sessions run here. | **Hard Disk Files:** Website source code, HTML/CSS/JS files, Images, Videos, Plugins, and Themes. |
| **Database** | Software (MySQL, PostgreSQL, MSSQL) running *inside* or alongside the Server. Acts as a ledger/locker for structured record-keeping. | **Tables (Rows & Columns):** Usernames, passwords, emails, user bios, comments, prices, transaction records (text/numbers). |
 * **Single vs. Multiple Computers:** Chhoti websites mein Server aur Database ek hi physical computer par chalte hain. Bari websites mein Web Server alag computer par hota hai aur Database Server secure private network ke andar alag physical computer par.
## 3. Ports & Protocols (Building & Doors Concept)
 * **Protocols:** Communication ke qawaid/languages (HTTP, HTTPS, FTP, SSH).
 * **Ports:** Ek hi Server (Computer) ke andar alag-alag services ke dedicated darwaze (numbered 1 to 65535).
   * **Port 80:** HTTP (Unsecure Web)
   * **Port 443:** HTTPS (Secure Web)
   * **Port 21:** FTP (File Transfer)
   * **Port 22:** SSH (Remote Administration)
   * **Port 3306:** MySQL Database
 * **Nmap Scan:** Target IP ke tamam ports knock karke pata lagata hai ke konsa darwaza (port) OPEN hai aur peeche konsi service chal rahi hai.
## 4. Firewalls & Security Infrastructure
 * **Network Firewall:** Server ke aage hota hai; IP addresses aur Port numbers (Layer 3/4) ko filter karta hai.
 * **Web Application Firewall (WAF) / Cloudflare:** Website ke aage (Reverse Proxy) hota hai; HTTP traffic (Layer 7) ko check karta hai taake malicious payloads (SQLi, XSS) ko filter kar sake.
 * **Server Isolation:** Single server par 100 websites chal rahi hon toh Linux User Permissions aur Containers (Docker/VMs) ek website ke compromise hone par baaqi 99 websites ko protect karte hain (jab tak admin misconfiguration ya kernel root exploit na ho).
## 5. Backend Code & Application Logic
 * **Backend Code (PHP, Python, Node.js):** Website ka dimaag. Browser se aane wali HTTP requests ko receive karta hai, business logic perform karta hai, aur Database ke sath communicate karta hai.
 * **Backend vs. Server:** Server wo physical/virtual space (environment) hai jahan Backend Code reside karke execute hota hai.
## 6. SQL Injection (SQLi) Fundamentals
 * **SQL (Structured Query Language):** Database se baat karne ki standard language. Standard SQL queries (SELECT, WHERE, UNION, INSERT) tamam major databases (MySQL, MSSQL, PostgreSQL) par 80-90% same hoti hain.
 * **Cause of SQLi:** Jab Backend Code user ke input ko bina sanitize/validate kiye direct SQL query ke andar concatenate (jod) deta hai. Is se "Data" tabdil ho kar "Command" ban jata hai.
 * **Database Role in SQLi:** Database innocent hota hai; wo Backend Code ki bheji hui query ko trusted command samajh kar execute kar deta hai.
 * **Types of SQLi:**
   1. **In-Band:** Error-Based, Union-Based (Data directly screen par nazar aata hai).
   2. **Inferential (Blind):** Boolean-Based, Time-Based (True/False ya delays se data extract hota hai).
   3. **Out-of-Band:** External DNS/HTTP requests ke zariye data exfiltrate hota hai.
 * **Primary Defense:** **Prepared Statements / Parameterized Queries**. Code aur Data ko pehle se alag treat kiya jata hai taake input kabhi executable command na ban sake.
## 7. Penetration Testing Core Foundation Pattern
```
[ FRONTEND ]         HTML, CSS, JavaScript (Client-side UI)
     │
     ▼
[ TRANSPORT ]        HTTP/HTTPS Protocols (Headers, GET/POST, Cookies, Sessions)
     │
     ▼
[ FIREWALL / WAF ]   Security Filtering (Cloudflare, ModSecurity)
     │
     ▼
[ SERVER & OS ]      Linux Administration, Port Services, Web Server (Apache/Nginx)
     │
     ▼
[ BACKEND LOGIC ]    PHP / Python / Node.js (Application Vulnerabilities)
     │
     ▼
[ DATABASE ]         MySQL / PostgreSQL (SQL Queries & Data Storage)

```
*Note: Primary target combo to start practical hands-on web security labs: **PHP + MySQL**.*

---

## 1. Kya JavaScript poori seekhne ki zaroorat nahi, sirf XSS payloads kafi hain?
HTML aapko aati hai toh yeh boht zabardast baat hai! Jahan tak JavaScript ki baat hai, toh aapko ek **Full-Stack Web Developer** ki tarah poori JS (jaise complex frameworks ya apps banana) seekhne ki bilkul zaroorat nahi hai.
Lekin sirf payloads rat lena bhi kaafi nahi hota. XSS ko ache se samajhne aur advanced filters ko bypass karne ke liye aapko kuch basic concepts clear hone chahiye:
 * **DOM (Document Object Model):** Yeh samajhna ke page ka structure JavaScript ke zariye kaise change hota hai.
 * **Sinks aur Sources:** Yeh pata ho ke data kahan se aa raha hai (location.search, document.URL) aur kahan execute ho raha hai (eval(), innerHTML).
 * **Basic Functions:** Jaise cookies access karna (document.cookie), requests bhejna, ya event handlers (onload, onerror).
Jab aapko ye basic cheezein samajh aa jayengi, toh aap sirf ratta lagane ke bajaye khud ke naye payloads bana sakenge!
## 2. Server ki koi language hoti hai? Apache aur Nginx configurations kya hain?
Nahi, Apache aur Nginx ki koi programming language nahi hoti. Yeh khud software hain jo C language mein likhe gaye hain aur yeh **Web Servers** kehlate hain—inke zariye hi website internet par live hoti hai aur user ki requests ko handle karti hai.
 * **Configurations kya hain?** Inki apni settings ki files hoti hain (jaise nginx.conf ya .htaccess), jismein server ko bataya jata hai ke website ki files kahan pari hain, URL routing kaise karni hai, aur security rules kya honge.
 * **Kya inhein yaad karna parta hai?** **Bilkul bhi nahi!** Duniya ka koi pentester ya developer inki configurations ko yaad nahi karta.
**Pentester ke taur par aapko kya pata hona chahiye?**
Aapko configurations **yaad** nahi karni, balk yeh pata hona chahiye ke **Server Misconfiguration** kya hoti hai. Misconfiguration ka matlab hai ke developer ya admin ne server ki setting mein koi ghalti chhor di ho; misconfigurations mein yeh cheezein aati hain:
 * **Directory Listing Enabled:** Agar yeh on ho, toh folder ki saari private files open browser mein dikh jati hain.
 * **Insecure Headers:** Security headers (jaise CORS ya CSP) theek se set na hona.
Aapka kaam configurations likhna nahi, balk yeh check karna hota hai ke kahan ghalat setting ki wajah se server leak ho raha hai!

Task 2 par aao, yeh bohot important concept hai kyunki cyber security mein jab tak tumhein ports aur unki states ka sahi tarah pata nahi hoga, tum scanning ka result nahi samajh sako gy.
Chalo isay asaan points mein breakdown karte hain aur phir questions ky answers dekhte hain.
## 🚪 TCP aur UDP Ports Kya Hain?
Jaise ek barri building mein har ek flat ka alag number hota hai, bilkul waise hi ek computer (IP Address) ky andar alag alag services (jaise website, email, file sharing) ko chalane ky liye **Ports** hote hain.
 * **TCP Port 80 / 443:** Default HTTP (Websites) ky liye use hota hai.
 * Ek IP address par ek waqt mein ek port par sirf **ek hi service** chal sakti hai.
## 🚦 Nmap ki 6 Port States (Bohat Important!)
Waisay toh ports ya toh **Open** hote hain ya **Closed**, lekin beech mein firewalls ki wajah sy Nmap total **6 states** report karta hai:
 1. **Open:** Service chal rahi hai aur listening mode mein hai (Hamein yahi chahiye hota hai).
 2. **Closed:** Port tak pohncha ja sakta hai, lekin agay koi service active nahi hai.
 3. **Filtered:** Subsy ahem! Iska matlab hai beech mein **Firewall** bethi hai jo Nmap ky packets ko block kar rahi hai. Nmap andaza nahi laga pa raha ky port open hai ya closed.
 4. **Unfiltered:** Port accessible hai, lekin Nmap yeh confirm nahi kar pa raha ky open hai ya closed (Yeh sirf ACK scan -sA mein aata hai).
 5. **Open|Filtered:** Nmap confuse hai ky port open hai ya phir firewall ki wajah sy filtered hai.
 6. **Closed|Filtered:** Nmap confuse hai ky port closed hai ya filtered hai.

## 📝 Task Questions ky Answers
Yahan tumhare questions ky exact answers hain jo tum TryHackMe par submit kar sakte ho:
### 1. Which service uses UDP port 53 by default?
> **DNS** (Domain Name System - jo website names ko IP addresses mein convert karta hai).
> 
### 2. Which service uses TCP port 22 by default?
> **SSH** (Secure Shell - remote terminal access ky liye use hota hai).
> 
### 3. How many port states does Nmap consider?
> **6** (Jaise upar hum ne discuss kiya).
> 
### 4. Which port state is the most interesting to discover as a pentester?
> **open** (Kyunki open port par hi koi service chal rahi hoti hai jismey hum vulnerability dhoond sakte hain).
> 

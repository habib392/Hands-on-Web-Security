## 🧐 Targets Batane Ke 4 Tareeqay
Jab aap Nmap chala rahe hote hain, to aap target ko alag-alag formats mein likh sakte hain:
 1. **List (Ek se zyada targets):** Aap simple space de kar alag-alag IPs ya domains likh sakte hain.
   * nmap 192.168.1.1 google.com facebook.com (Yeh in teeno ko scan karega).
 2. **Range (Aik hisse ki limit):** Agar aap ko aakhri number par range deni ho.
   * nmap 10.11.12.15-20 (Yeh 15, 16, 17, 18, 19, aur 20... yaani total 6 IPs scan karega).
 3. **Subnet (Poora network block):**
   * nmap 192.168.1.0/24 (Yeh us network ki saari 256 IPs ko scan karega).
 4. **File Input (-iL):** Agar aap ke paas 500 IPs ki ek text file hai (jaise targets.txt), to aap poori list terminal par likhne ki bajaye Nmap ko file pakra dete hain.
   * nmap -iL targets.txt (Nmap khud file khol kar saari IPs scan kar lega).
## 🛠️ Aik Bohot Useful Flag: -sL (Scan List)
Yeh flag cyber security mein bohot kaam aata hai. Farz karein aap ne Nmap ko ek subnet diya jaise /24 (256 IPs). Lekin aap scan shuru karne se pehle sirf yeh check karna chahte hain ke **Nmap asal mein kaun kaun si IPs scan karne ja raha hai, bina un par koi packet bheje (No actual scan).**
 * **Command:** nmap -sL 10.200.6.0/24
 * **Fayda:** Nmap chup-chap un saari IPs ki list terminal par dikha dega aur sath hi unka **Reverse DNS (rDNS)** check karke unke naam bhi nikal lega (jaise humne pichle task mein parha tha).
 * **Stealth Tip:** Chunki yeh target machines par koi packet nahi bhejta, isliye target ko pata hi nahi chalta ke koi unhein dekh raha hai. Lekin haan, DNS server par queries jati hain. Agar aap chahte hain ke DNS query bhi na jaye, to sath -n laga dein: nmap -sL -n 10.200.6.0/24.
## 🚀 Lab Shuru Karne Ka Time
Ab is text ke mutabiq aap ki practical lab shuru ho rahi hai. TryHackMe ke page par aapko ek target network milega jismein ek **Windows machine** hai aur ek **Ubuntu (Linux) machine** hai.
 1. Page par upar green color ka **"Start"** ya **"Start Machine"** button hoga, use dabayein aur 2 minute wait karein.
 2. Apni **AttackBox** (Linux terminal jo TryHackMe deta hai) open karein.
 3. Ab hum un machines par host discovery chala kar check karenge ke unki IPs kya hain.

---

## Question/Answers 

### Question 1: What is the first IP address Nmap would scan if you provided 10.10.12.13/29 as your target?
 * **Answer:** 10.10.12.8
 * **Explanation:** Jab aap /29 use karte hain, to iska matlab hota hai ke subnet ka block size **8** hai (kyunki 32 - 29 = 3 bits host ke liye hain, aur 2^3 = 8).
   Ab agar hum 10.10.12.0 se 8 ke blocks banayein:
   * Block 1: 10.10.12.0 se 10.10.12.7
   * Block 2: 10.10.12.8 se 10.10.12.15
   Chunki aapki target IP 10.10.12.13 is doosre block mein aati hai, aur Nmap hamesha poore subnet ki network ID se scanning shuru karta hai, isliye is block ki sabse pehli IP **10.10.12.8** hogi.
### Question 2: How many IP addresses will Nmap scan if you provide the following range: 10.10.0-255.101-125?
 * **Answer:** 6400
 * **Explanation:** Nmap mein jab ranges di jati hain, to hum dono badalte hue octets (hisson) ki total IPs ko aapas mein multiply karte hain.
   * Pehla badalta hua hissa: 0-255 (Total 256 IP addresses)
   * Doosra badalta hua hissa: 101-125 (Total 25 IP addresses, kyunki 125 - 101 + 1 = 25)
   Ab in dono ko multiply karein:
   

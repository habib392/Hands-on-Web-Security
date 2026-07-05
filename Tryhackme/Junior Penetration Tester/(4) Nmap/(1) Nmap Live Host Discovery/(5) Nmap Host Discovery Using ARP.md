Yeh section bohot hi behtareen tareeqay se Nmap ke backend logic ko samjha raha hai ke Nmap default halat mein kab aur kaun sa scan automatic select karta hai. Chalein isko aasan Roman Urdu mein break-down karte hain:
## 🧐 Pehla Hissa: Nmap Default Halat Mein Kaise Sochta Hai?
Nmap ko chalane wale user ke privileges (Root/Sudo vs Normal User) aur target network ki location ke mutabiq 3 main scenarios bante hain:
### 1. Privileged User + Local Network (Same Subnet)
 * **Nmap Action:** Nmap chup-chap **ARP requests** bhej kar host discovery karega.
 * **Fayda:** Yeh sabse tez aur accurate hota hai kyunki firewalls isko block nahi kartin.
### 2. Privileged User + Outside Network (Remote/Internet Target)
 * **Nmap Action:** Nmap 4 alag-alag checks bhejta hai taaki koi na koi rasta nikal aaye:
   1. **ICMP Echo Request** (Normal Ping)
   2. **TCP ACK** packet port **80** par
   3. **TCP SYN** packet port **443** par
   4. **ICMP Timestamp Request**
### 3. Unprivileged User (Normal User bina sudo ke) + Outside Network
 * **Nmap Action:** Chunki normal user raw packets (SYN/ACK) craft nahi kar sakta, isliye Nmap majbooran OS ke standard **TCP 3-way handshake** ka use karta hai aur ports **80** aur **443** par SYN packets bhejta hai.
## 🛠️ Doosra Hissa: ARP Scan ke Flags aur Logic
 * **nmap -sn TARGETS**: Yeh poore Nmap mein host discovery (Ping Scan) ka standard flag hai. Iska matlab hai: *"Sirf live hosts dhoondo, unke ports scan mat karo."*
 * **nmap -PR -sn TARGETS**: Yahan -PR explicitely Nmap ko kehta hai ke sirf **ARP scan** hi use karo.
 * **Wireshark Analysis:** Jab ARP scan chalta hai, to Nmap hamare machine ke MAC address se pure network ke **Broadcast Address (ff:ff:ff:ff:ff:ff)** par sequentially (aik ke baad aik) packets bhejta hai. Jo machine up hoti hai, woh apna MAC address send kar deti hai.

---

## Question/Answer
Aap se text ke aakhir mein simulator ke scan report se aik sawaal pucha gaya hai:
**Question:** How many hosts are found alive after scanning the 10.49.153.101/24?
Agar aap text mein di gayi Nmap terminal ki final line ko ghaur se dekhein:
> Nmap done: 256 IP addresses (1 host up) scanned in 10.51 seconds
> 
 * **Answer:** **1**
*(Logic: Scan report mein clear likha hai ke 256 IP addresses check karne ke baad sirf **1 host up** mila hai, jo ke khud AttackBox ki apni IP thi).*
Is **1** ko text box mein enter karein, 
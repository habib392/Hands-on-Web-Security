Ab Nmap series ky iss doosray room ko bilkul simple aur short points mein samajhte hain. Yeh room cyber security mein **Port Scanning** ki jaan hai.
Pichlay room mein tum ne seekha tha ky network par kaun kaun sy computer/hosts online hain (Live Host Discovery). Ab iss room ka maqsad yeh dekhna hai ky un online computers ky kaun sy **Ports open** hain aur kaun sy **closed** hain, taakay vulnerabilities ka pata lagaya ja sakay.

## 🎯 Main Learning Objectives (Hamein Kya Seekhna Hai?)
Iss room mein majorly teen types ky port scans ko deeply discuss kiya gaya hai. Jab tum inko samajh lo gy, toh scan rate aur target ports ko control krna bhi aa jaye ga.
### 1. TCP Connect Scan (-sT)
 * **Yeh kya hai?** Yeh sab sy basic scan hai jo target ky sath poora **TCP 3-Way Handshake** complete karta hai.
 * **Process:** Tumhara system target ko SYN bhejta hai > Target SYN-ACK deta hai > Tumhara system ACK bhej kar connection establish karta hai aur phir band kar deta hai.
 * **Fayda/Nuqsan:** Yeh scan bohot reliable hai lekin yeh target ky system logs mein record ho jata hai (yani yeh stealthy/chupa hua nahi hota).
### 2. TCP SYN Scan (-sS)
 * **Yeh kya hai?** Isay **Half-Open Scan** ya **Stealth Scan** bhi kehte hain. Yeh poora connection complete nahi karta.
 * **Process:** Tumhara system SYN bhejta hai \rightarrow Target agar open ho toh SYN-ACK deta hai \rightarrow Lekin tumhara system ACK bhejny ky bajaye **RST (Reset)** bhej kar connection wahin tor deta hai.
 * **Fayda:** Yeh bohot fast hota hai aur puranay ya basic firewalls isay asaani sy pakar nahi paate logs mein. Default Nmap scan yahi hota hai (agar tum sudo user ho).
### 3. UDP Scan (-sU)
 * **Yeh kya hai?** TCP ky bar-aks, UDP ek connectionless protocol hai (jaise DNS, DHCP). Un ports ko scan krny ky liye yeh use hota hai.
 * **Process:** Nmap target ko UDP packet bhejta hai. Agar port closed ho, toh target aksar ICMP Port Unreachable ka error deta hai. Agar koi jawab na aaye, toh Nmap isay open|filtered show karta hai.
 * **Nuqsan:** Yeh bohot slow hota hai kyunki UDP mein koi handshake nahi hota, is liye confirmations mushkil hoti hain.
## 🛠️ Performance aur Customization Options
Iss room mein tum mazeed yeh options bhi seekho gy:
 * **Port Selection:** Ek specific port ya range ko kaise scan krna hai (e.g., -p 80,443 ya -p- saare 65535 ports ky liye).
 * **Scan Rate:** Scan ki speed ko kaise control krna hai (--min-rate ya --max-rate bhej kar packets per second set krna).
 * **Parallel Probes:** Ek waqt mein kitni probes parallel bhejni hain taakay scan jaldi khatm ho.
## 🚀 Lab/Prerequisites Guide
 * **Prerequisite Rooms:** Room kehta hai ky agay barhnay sy pehle tumhein *Live Host Discovery* aur *Network Services* ka thora andaza hona chahie (jo ky tumhein basic level par pehle sy hai).
 * **Hands-on Task:** Task 4 mein tumhein practical lab krni hogi. Us ky liye tumhein screen par diye gaye **Start Machine** aur **Start AttackBox** ky buttons par click krna hoga taakay tumhara virtual environment ready ho jaye.

## ⚔️ The Core Concept: Attacker vs Defender
Sun Tzu ki boht purani aur mashhoor qoutation hai: *"Agar tum dushman ko aur apny aap ko janty ho, toh tumhari jeet pakki hai."*
Cyber security mein isky do pehlu hain:

 * **Attacker (Ethical Hacker/Bug Bounty Hunter):** Tum target ki kamzoriyan (vulnerabilities) dhoondnay ky liye unka data jama krty ho.

 * **Defender:** Tum yeh check krty ho ky dushman (hacker) ko bahaar sy tumhari company ka kya kya data mil rha hai, taakay tum us exposure ko kam sy kam (minimise) kr sako.

Reconnaissance (Recon) hamesha kisi bhi cyber attack framework (jaisy **Unified Kill Chain** ya **Cyber Kill Chain**) ka sab sy **pehla phase** hota hai.

## 🔍 1. Passive Reconnaissance (Khufia Tareeqa)
Is mein target ko bilkul touch nahi kiya jata. Koi packet unky server par nahi jata, is liye pakray jany ka **zero risk** hota hai. Yeh bilkul aisy hai jaisy door khray ho kar doorbeen (binoculars) sy dushman ka ilaqa dekhna.

### Common Passive Activities (Jo hum dhoondty hain):

 * **Public DNS Records:** Open resolvers sy domain ki details (IP addresses, Mail servers) nikalna.

 * **Certificate Transparency Logs:** crt.sh jaisi sites sy subdomains ka pata lagana.

 * **LinkedIn/Job Postings:** Company ki job vacancies dekh kar andaza lagana ky woh kaun si technology (Python, AWS, Docker) use kr rhy hain.

 * **GitHub Repositories:** Public code check krna ky kahin kisi developer ny galti sy passwords ya API keys toh expose nahi kr dein.

 * **Shodan/Censys:** IoT devices aur servers ki bahaar sy mili hui details check krna.

## 🎯 2. Active Reconnaissance (Direct Interaction)
Is mein tum direct target ky systems ya logon sy interact krty ho. Is mein pakray jany ka khatra boht zayada hota hai kyun ky firewalls (WAF) aur Intrusion Detection Systems (IDS/IPS) tumhari activity ko **log aur block** kr sakti hain. **Bagair permission active recon krna illegal hai!**

### Common Active Activities:

 * **Live Hosts Check:** ping (ICMP requests) ya ARP requests bhejna.
 * **Port Scanning:** Nmap ya masscan chala kar open ports aur services ka pata lagana.

 * **Web Fuzzing:** Directory brute-forcing krna (jaisy gobuster ya dirsearch chalana).

 * **Social Engineering:** Company ky kisi bande ko call krna (vishing) ya phishing email bhejna.

 * **Physical Approach:** Kisi ke pehly pehly building mein ghus jana (tailgating).

> ⚠️ **Zaroori Note:** Agar tum company ky kisi employee sy directly baat krty ho (chahe kisi party mein milo aur baton baton mein unki IT tech stack ka pooch lo), toh woh bhi **Active Recon** mein hi aaye ga, kyun ky tum ne direct contact kiya hai.
> 
## 🛡️ Defender Tip
Aaj kal ki companies khud bhi apny upar automated OSINT tools aur Shodan alerts laga kar rakhti hain, taakay unhein pata rahy ky unka kitna data internet par publicly para hua hai aur woh usay hide kr sakein.

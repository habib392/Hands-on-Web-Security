Shell access ko asan alfaz main samajhne ke liye pehle yeh samjhna zaroori hai ke **Shell** kya hota hai. Shell kisi bhi operating system (Linux ya Windows) ka woh interface ya command-line tool hota hai (jaise Bash, Terminal, ya Command Prompt/PowerShell) jo apko operating system ke core (kernel) se direct baat karne aur commands execute karne ki ijazat deta hai.
Jab penetration testing ya ethical hacking ki baat hoti hai, toh **Shell Access** ka matlab hota hai target server ya machine ke Command Line Interface (CLI) ka control hasil kar lena.

### Shell Access Kis Tarah Hasil Hota Hai?
 1. **Vulnerability Exploitation:** Ap application ya server main koi weakness dhoondte hain (jaise Unrestricted File Upload, Command Injection, ya SQL Injection).
 2. **RCE (Remote Code Execution):** Iss vulnerability ki madad se ap server par apni marzi ka code ya command run karne ki kabil ho jate hain.
 3. **Payload Execution:** RCE milne ke baad ap ek specific payload (jaise malicious script ya reverse shell payload) run karte hain.
 4. **Shell Session:** Iss payload ki wajah se apko target system ka Terminal/Prompt mil jata hai jahan ap commands chala kar files read kar sakte hain, privileges escalate kar sakte hain, ya system ko further inspect kar sakte hain.
### Shell Access Ki Amm Kismein (Types of Shells)
Penetration testing main aksar teen tarah ke shells use hotey hain:
 * **Web Shell:** Ek choti si script (jaise PHP, ASPX, ya JSP file) jo server par upload kar di jati hai. Iss script ke browser interface se ap server par commands chala sakte hain.
 * **Reverse Shell:** Target server apke attacker system (jaise Kali Linux) ke sath connection create karta hai. Yeh firewalls ko bypass karne ke liye sab se zyada use hota hai.
 * **Bind Shell:** Attacker direct target server ke ek khule hue port par connect ho kar shell access hasil karta hai.

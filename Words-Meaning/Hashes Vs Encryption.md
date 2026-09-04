**Hashes** aik unique digital footprint hota hai jo sensitive data (jaise passwords) ko secure rakhne ke liye generate kiya jata hai. Yeh one-way process hota hai—data se hash banta hai, lekin hash se wapas asli data hasil nahi kiya ja sakta (maslan SHA-256 ya MD5).
**Encryption** data ko safe rakhne aur secure communication ke liye use hoti hai. Yeh two-way process hai jisme readable plaintext ko unreadable ciphertext banaya jata hai aur sahi key (Password/Key) se wapas decrypt kiya ja sakta hai (maslan AES ya RSA).
### In Dono Ka Difference Aur Usage
 * **Usage:** Hashes ko passwords store karne aur file ki integrity verify karne ke liye har jagah use kiya jata hai. Encryption ko sensitive data (credit card information, emails) store karne aur internet transmission (HTTPS) par traffic ko secure rakhne ke liye use kiya jata hai.
 * **Main Difference:** Hashes ko kabhi wapas reverse (decrypt) nahi kiya ja sakta, jab ke Encryption ko sahi key se decryption key ke zariye reverse kiya ja sakta hai.
### Burp Suite Se Decode Kya Hota Hai?
Burp Suite ka **Decoder tab** hashing ya encryption ko b bina key ke "crack" nahi karta, balke yeh web formats ko handle karta hai:
 * **Decode Ho Sakta Hai:** Encoding Formats jaise **Base64, URL Encoding, HTML Encoding, Hex, Binary**. (Note: Base64 ya URL Encoding encryption nahi hoti, yeh sirf data transmission Format hota hai).
 * **Decode Nahi Ho Sakta:** Strong Encryption (jab tak decryption key na ho) aur Hashes (in ko decode nahi balke Hashcat/John the Ripper se brute-force/crack kiya jata hai).
### Web Pentester Ke Liye Kya Zaroori Hai?
As a Web Penetration Tester, aap ko **dono par focus karna hai**, lekin shuruaat aur daily practical work ke liye **Hashes par ziada grip honi chahiye**.
 * **Hashes:** Web application testing me aap ko database dumps se hashes milenge (e.g., MD5, SHA-1, Bcrypt). Aap ko in ko identify karna, crack karna (Hashcat se) aur hashing weaknesses (jaise bina salt ke hashes) test karna aana chahiye.
 * **Encryption:** Web app level par aap ko SSL/TLS issues, JWT token decryption, weak Ciphers, aur insecure client-side encryption test karne ke liye basic-to-intermediate samajh kafi hoti hai.

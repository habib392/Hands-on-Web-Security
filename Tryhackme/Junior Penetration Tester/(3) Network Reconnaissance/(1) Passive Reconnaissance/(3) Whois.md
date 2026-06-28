## 🛠️ WHOIS Kya Hai? (The Legacy Protocol)
WHOIS aik aisa tareeqa (protocol) hai jis sy hum internet par kisi bhi domain (jaisy tryhackme.com) ki registry details nikalte hain.
 * **Port:** Yeh **TCP Port 43** par kaam krta hai.
 * **Kaun chalata hai?** Domain Registrars (jaisy Namecheap, GoDaddy, Domain.com) is data ko maintain krty hain.
### WHOIS Data sy Kya Kya Milta Hai?
 1. **Registrar:** Kis company sy domain kharida gaya (e.g., Namecheap).
 2. **Dates:** Domain kab bana (**Creation**), kab tabdeeli hui (**Updated**), aur kab khatam hoga (**Expiration**).
 3. **Name Servers:** Woh DNS servers jo is domain ko handle kr rhy hain (yeh agly attacks ya mapping ky liye targets ho sakty hain).
 4. **Status Codes:** Jaisy clientTransferProhibited, iska matlab hai domain locked hai aur koi isay unauthorized transfer (hijack) nahi kr sakta.
 5. **Abuse Contact:** Agar is domain sy koi cyber attack ya spamming ho rhi ho, toh registrar ko report krny ky liye email/phone number.
> 🔒 **Privacy Alert (GDPR 2018):** Pehly zamane mein owner ka asli naam, phone aur email mil jata tha. Magar ab GDPR privacy laws ki wajah sy details hide hoti hain aur wahan **"Withheld for Privacy"** likha aata hai.
> 💡 **Attacker Trick:** Hackers purana data dekhnay ky liye **whoxy.com** jaisi historical WHOIS services use krty hain, jahan sy purane owners ya purane name servers ka pata chal jata hai.
> 
## 🚀 WHOIS ka Naya Bhai: RDAP (Registration Data Access Protocol)
**28 January 2025** ko ICANN ny purane WHOIS protocol ko officially khatam (sunset) krna shuru kr diya aur uski jagah **RDAP** ko naya standard bana diya.
### RDAP Kyun Behtar Hai?
 * **Secure:** Yeh simple TCP ki jagah **HTTPS** use krta hai.
 * **Machine Readable:** Iska output **JSON** format mein hota hai, jisay computer programs aur scripts asaani sy parh sakti hain.
 * **Better Privacy:** Is mein alag alag levels par privacy controls hoty hain.
## 💻 Practical Commands (Jo Labs mein Kaam Aayein Gi)
### 1. Traditional WHOIS Query
Terminal mein simple yeh command chalti hai:
```bash
whois tryhackme.com

```
*Iska output dekh kar tum andaza laga sakty ho ky TryHackMe **2018** mein register hua tha aur Namecheap sy liya gaya tha.*
### 2. Modern RDAP Query (curl + jq)
Chunkay RDAP JSON data deta hai, hum curl sy request bhejte hain aur jq (JSON Processor) use krty hain output ko saaf suthra dekhnay ky liye:
```bash
curl -s https://rdap.verisign.com/com/v1/domain/tryhackme.com | jq .

```
*(Agar tum apny system par ho aur jq nahi chal rha, toh sudo apt install jq kr lena).*
## 🎯 Attacker Mindset: Hum Kya Dhoond Rahy Hain?
 * **Dates:** Agar koi domain jald expire hony wala hai, toh company ky employees ko target kr ky renewal phishing emails bheji ja sakti hain.
 * **Name Servers:** Target ka infrastructure samajhnay mein madad milti hai.


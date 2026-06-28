Yeh task boht hi dilchasp hai aur **Shodan.io** cyber security ki dunya mein aik boht bara aur behtareen tool hai!
Aam tor par Google sirf web pages (text, images waghaira) ko index krta hai, lekin **Shodan** poore internet par chalne wali **devices** (servers, routers, security cameras, IoT devices, smart TVs) ko scan krta hai. Yeh lagatar internet ky open ports sy unka data (banners) jama krta rehta hai.
Chunkay Shodan ny yeh scanning pehly sy ki hoti hai, is liye jab hum is par kuch search krty hain toh hum target ko touch nahi kr rhy hoty, balkay Shodan ka purana database parh rhy ہوتے hain. Isliye yeh **100% Passive Recon** hai!
### 🔍 Shodan Filters (Jo Agay Kaam Aayein Gy)
Shodan par advanced searching ky liye kuch filters use hoty hain:
 * hostname:target.com — Kisi specific domain ky assets dekhnay ky liye.
 * org:"Company Name" — Kisi company ky naam sy unky servers dhoondnay ky liye.
 * port:22 — Sirf woh devices dhoondnay ky liye jin par SSH open ho.
 * country:PK — Kisi specific country (jaisy Pakistan) ki devices dekhnay ky liye.
### 🎯 Question Solution
Sawaal mein pucha gaya hai:
> **According to Shodan.io, what is the first country in the world in terms of the number of publicly accessible Apache servers?**
> *(Shodan.io ky mutabiq, dunya mein kaun sa mulk pehle number par hai jahan sab sy zyada publicly accessible Apache servers hain?)*
> 
#### Answer nikalne ka tareeqa:
 1. Apne browser mein **shodan.io** kholo.
 2. Search bar mein simple likho: **product:Apache** (ya sirf **Apache** likh kr search kr lo).
 3. Search results ky left side (baayein taraf) par tumhein **"Top Countries"** ki aik list nazar aaye gi, jahan sab sy zyada count wale mulk ka naam sab sy upar hoga.
Dunya mein sab sy zyada internet infrastructure aur servers **United States** (US) mein hain, is liye top par wahi aata hai.
👉 Iska answer check karo: **United States**

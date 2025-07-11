**Sensitive Data Exposure** tab hoti hai jab koi website apna **sensitive (nazuk)** data properly hide nahi karti — ya usay frontend mein chhor deti hai, jahan har banda “View Page Source” se dekh sakta hai.

Ab tak tu samajh chuka hai ke websites HTML tags se banti hain, aur unka source code har banda dekh sakta hai.

Kabhi kabhi developer bhool jata hai:

* Login credentials (jaise temporary usernames/passwords)
* Secret links (jo private parts of site ke liye hotay hain)
* Ya aur sensitive info HTML ya JavaScript mein chhor deta hai

![HTML SOURCE](https://github.com/habib392/ImagesSS/blob/d0cbdf24ce46d9ca9fbfc076deac646cc4ff435b/html_source.png)

Ye data agar attacker dekh le, toh wo site ke doosray hisson tak pahunch sakta hai.
Misal ke taur pe:

* Kisi HTML comment mein likha hota hai: `<!-- username: admin, password: test123 -->`
* Agar tu source code dekhe aur ye credentials mil jayein, tu login kar sakta hai ya backend ka access le sakta hai.

---

### Isliye:

Jab bhi tum kisi web app ki security check kar rahe ho, toh **sabse pehla kaam ye karo ke "View Page Source"** karke dekho — kahin kuch **hidden login info ya secret links** toh nahi chhupay huay.

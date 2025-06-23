JavaScript main agr hum **alert()** use krty hain ky website main XSS execute hoo rha hai ya nhi agr execute hoo rha hua too aik pop up ajaye ga

**prompt()** hum kisi command ky sath ius waqt use krty hain jab hamy user sy input chahie hota hai example agr hum likhty hain prompt("Enter your password") too website py aik display hota hai Enter Your Password phir user ius main apna password daaly ga

**var** hum taab lagaty hain jab hum user ki value ko apny database main store karna chahty hoon

**let** var aur let dono value store karte hain — lekin let zyada safe hota hai.

## Difference Between Var/let

Value store karna

**var**

var name = "Habib";

- Old JavaScript version ka style hai.

- Function-level scope rakhta hai.

**let**

let age = 18;

- New aur modern style hai (ES6+).

- Block-level scope rakhta hai.

### Quick Summary

**alert()**	Popup show karta hai	

XSS main use: XSS payload test karna

**prompt()**	User se input leta hai

XSS main use: Fake login / phishing

**var or let**	Value store karta hai
XSS main use: Cookie ya user data store karna

**if / else** Logic lagana
XSS main use:	Kab kya run ho

**document.cookie**	User ki cookies nikalna
XSS main use:	Session hijack

**fetch()** Data dusri site pe bhejna
XSS main use: Data leak (exfiltrate)

**img.src** 	Image ke zariye request bhejna	
XSS main use: Alternate data leak meth

if else bhi 100% samj agya



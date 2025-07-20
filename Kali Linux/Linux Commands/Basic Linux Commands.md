# 🐧 **Linux Basic Commands for Beginners **

## 🔹 `ls` – List Files & Folders

Jis folder ke andar hoon, uske andar kya kya files ya folders hain, woh dekhne ke liye `ls` use hoti hai.

```bash
ls
```

---

## 🔹 `cd` – Change Directory

Ek folder se doosre folder mein jaane ke liye `cd` use hoti hai.

```bash
cd Downloads
```

---

## 🔹 `pwd` – Present Working Directory

Abhi hum kis location (path) mein hain, usay dekhne ke liye.

```bash
pwd
```

---

## 🔹 `help` – Built-in Command Help

Shell built-in commands ka help dekhne ke liye.

```bash
help cd
```

---

## 🔹 `--help` – External Commands Help

Kisi bhi command ke aage `--help` lagao, uska chhota help guide milta hai.

```bash
ls --help
```

---

## 🔹 `man` – Manual (Detailed Guide)

Command ka full manual dekhne ke liye.

```bash
man ls
```

> Exit karne ke liye `q` press karo.

---

## 🔹 `dir` – List Directory Contents (Alternative of `ls`)

`ls` ki jagah `dir` bhi use kar sakte ho.

```bash
dir
```

---

## 🔹 `mkdir` – Make Directory

Naya folder banane ke liye.

```bash
mkdir myfolder
```

---

## 🔹 `cp` – Copy Files or Folders

Kisi file ya folder ko copy karne ke liye.

**File copy:**

```bash
cp file.txt backup.txt
```

**Folder copy:**

```bash
cp -r folder1 folder2
```

---

## 🔹 `mv` – Move ya Rename

File ko ek jaga se doosri jaga le jaana ya rename karna.

**Move:**

```bash
mv file.txt /home/habib/Desktop/
```

**Rename:**

```bash
mv old.txt new.txt
```

---

## 🔹 `rm` – Remove (Delete)

File ya folder ko delete karne ke liye.

**File:**

```bash
rm file.txt
```

**Folder:**

```bash
rm -r foldername
```

⚠️ Warning: Yeh permanently delete karta hai!

---

## 🔹 `sudo su` – Root Access

Admin (root) user banne ke liye.

```bash
sudo su
```

> Pentesting mein jab tu privilege escalate karega, yeh command kaam aayegi.

---

## 🔹 `nano` – Terminal Text Editor

Simple text editor jo terminal ke andar kaam karta hai.

```bash
nano file.txt
```

**Save:** Ctrl + O
**Exit:** Ctrl + X

---

## 🔹 `cat` – File ka Content Dekhna

File ke andar kya likha hai, woh dekhne ke liye.

```bash
cat file.txt
```

---

## 🔹 `gedit` – GUI Text Editor

Graphical editor jo Linux ke desktop environment mein use hota hai.

```bash
gedit file.txt
```

> Agar tu terminal-only system use kar raha hai (jaise server ya VPS), to `gedit` nahi chalega — uske liye `nano` use kar.

---

## 🔹 `chmod` – File/Folder Permissions Change Karna

File ya script ko executable banane ke liye ya permissions set karne ke liye.

**Executable banane ke liye:**

```bash
chmod +x script.sh
```

**Number based permissions:**

```bash
chmod 755 file.txt
```

> Pentesting mein jab tu script chalayega ya unauthorized access lena chahega, to `chmod` kaafi important hai.

---

# ✅ **Pentesting Tips for These Commands**

| Command                | Pentesting Use                           |
| ---------------------- | ---------------------------------------- |
| `ls`                   | Directory enumeration                    |
| `cd`, `pwd`            | Path traversal during enumeration        |
| `sudo su`              | Privilege escalation                     |
| `nano`, `cat`, `gedit` | File read/write operations               |
| `chmod`                | Exploit scripts ko executable banana     |
| `rm`, `mv`, `cp`       | File manipulation during LFI/RFI testing |


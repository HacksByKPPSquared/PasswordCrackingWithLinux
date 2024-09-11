# 🔐 Password Cracking with Linux 🐧💥

Welcome to **My Lab**, where we dive headfirst into the world of password cracking on Linux. Grab your (virtual) hacking hoodie, because in this lab, we’re going to create user accounts, set passwords, and then *crack* those passwords using some of the best tools Linux has to offer. Let’s get cracking! 😎

---

## 1️⃣ Cracking Linux Passwords

### 1.1 Creating User Accounts and Groups 👥
We start off nice and easy—creating some new users and groups on our **Kali** machine, because what fun is cracking passwords if there’s no one to crack? 😏

1. **Launched the Kali VM** and logged in as the all-powerful root user.  
2. Created two groups: **juniors** and **seniors**, because even hackers love hierarchy. 💼  
3. Added users:  
   - **Elmo** and **Oscar** joined the **seniors** group (because they’ve seen things). 🧓  
   - **Lisa** and **Homer** joined the **juniors** group (they’re new to the game). 🍼  
4. Set some simple passwords for each user—because we all know weak passwords are a hacker’s dream. 😏
   - **Elmo**: `123123`  
   - **Oscar**: `sanjose`  
   - **Lisa**: `academic`  
   - **Homer**: `acapulco`

### 1.2 Cracking Passwords Using John the Ripper 🦾

Now that we’ve set our users up for failure (password security is *important*, folks!), it’s time to unleash **John the Ripper**—the password-cracking tool that makes weak passwords tremble in fear. 👻

1. Listed the **available options** with `john --help` because knowledge is power, right? 💡  
2. Ran **John the Ripper** against our `/etc/shadow` file using a wordlist to see how long it takes to break our poor users’ passwords. Spoiler: not very long! ⏳

---

## 2️⃣ Cracking Windows Passwords 🖥️🔓

### 2.1 Cracking Windows Passwords Using Hashcat 🐱

Next up, we target **Windows**—because why should Linux have all the fun? Using **Hashcat**, we extracted the NT hashes from the Windows system and attacked them with a dictionary wordlist.

1. Switched to **Kali**, moved to the `/tmp/hashes` directory, and prepared to do some damage. 🛠️  
2. Parsed out the NT hashes from the **winhashes** file, saving them to the **nthashes** file.  
3. Used **Hashcat** with the passlist dictionary to crack the hashes. 💥

---

## 3️⃣ Obtaining and Cracking /etc/shadow 🕵️‍♂️

### 3.1 Obtaining the /etc/shadow Remotely 🌐

We also took a crack (pun intended) at grabbing the **/etc/shadow** file remotely from a **DVL** (Damn Vulnerable Linux) system. Why? Because hacking is all about *remote access*, right? 😉

1. Logged into the DVL server as root and started the **FTP service**.  
2. From **Kali**, we FTP’d into the DVL server, navigated to the `/etc` directory, and grabbed the **shadow** file.  
3. Transferred the file back to our **Kali** system—ready for cracking! 🏴‍☠️

### 3.2 Cracking /etc/shadow With Johnny 🎮

Once we had the shadow file, it was time to let **Johnny** (the GUI version of John the Ripper) do its thing. This is cracking, but with a shiny interface. ✨

1. Launched **Johnny**, loaded the shadow file, and selected **Wordlist mode**.  
2. Used our trusty **passlist** wordlist, clicked **Start Attack**, and watched Johnny work its magic. 🧙‍♂️  
3. Once the progress bar hit 100%, we reviewed our cracked passwords like a pro! 🔓🎉

---

## 🔧 Tools Used:

- **Kali Linux**: The ultimate hacker’s playground. 🐉  
- **John the Ripper**: The OG of password cracking. 🔨  
- **Hashcat**: Because Windows passwords deserve to be cracked too. 🖥️🐱  
- **Johnny**: A friendlier face for John the Ripper, with a GUI to boot. 🎮  
- **FTP**: File Transfer Protocol—because grabbing files remotely is what we do. 🌐

---

## 🌈 Why This Lab Matters:

Understanding password security is *critical* in the world of cybersecurity. In this lab, we explored just how easy it is to crack weak passwords (hint: **super easy**), and how attackers can gain access to sensitive data. Knowledge is power—so let’s use this power for good! 💡🔐

---

💡 **Pro-tip**: Always use strong, unique passwords for each account, and never underestimate the power of password managers! Trust us, you don’t want to be like Elmo with his `123123`. 😬🔑

---

Ready to crack some passwords and level up your security game? Let’s go! 💻🚀
## 👉🏾[Lab Walkthrough](https://github.com/Kpierre03/PasswordCrackingWithLinux/edit/main/PasswordCracking.md)

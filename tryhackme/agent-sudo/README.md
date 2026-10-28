# Agent Sudo


Description:

You found a secret server located under the deep sea. Your task is to hack inside the server and reveal the truth. 

---

# Task 1: Author Note

Welcome to another THM exclusive CTF room. Your task is simple, capture the flags just like the other CTF room. Have Fun!

If you are stuck inside the black hole, post on the forum or ask in the TryHackMe discord.

---

# Task 2: Enumerate

Enumerate the machine and get all the important information

How many open ports?

![Screenshot 2025-08-19 at 10.05.27 PM.png](images/01-screenshot.png)

**ANSWER: 3**

How you redirect yourself to a secret page?

**ANSWER: user-agent**

What is the agent name?

We head to the Website and see this

![Screenshot 2025-08-19 at 10.21.32 PM.png](images/02-screenshot.png)

We can use curl -A to change the user-agent like the following:

```bash
 curl -A "R" -L 10.201.104.251
```

![Screenshot 2025-08-19 at 10.23.50 PM.png](images/03-screenshot.png)

I tried these with C and got something

![Screenshot 2025-08-19 at 10.24.46 PM.png](images/04-screenshot.png)

---

# Task 3: Hash cracking and brute-force

Done enumerate the machine? Time to brute your way out.

FTP password?
For this we are going to use hydra

```bash
hydra -l chris -P /usr/share/wordlists/rockyou.txt ftp://10.201.104.251
```

![Screenshot 2025-08-19 at 10.32.40 PM.png](images/05-screenshot.png)

**ANSWER: crystal**

Zip file password

I went and ftp into chris account with the password we acquired. There was some files so we got them into our vm

![Screenshot 2025-08-19 at 10.41.39 PM.png](images/06-screenshot.png)

No we use binwalk in order to scan a file as a binary.

![Screenshot 2025-08-20 at 11.28.45 AM.png](images/07-screenshot.png)

I tried to unzip the .zip file but i got an error

![Screenshot 2025-08-20 at 11.52.15 AM.png](images/08-screenshot.png)

So lets zip2john in order to get the hashes and try to get the hashes in order to get the password and we get alien

![Screenshot 2025-08-20 at 12.11.41 PM.png](images/09-screenshot.png)

steg password?

We see what was on the .zip and cat  the file

![Screenshot 2025-08-20 at 12.12.18 PM.png](images/10-screenshot.png)

**QXJlYTUx** this is encrypted so we go to cyberchef and use magic on the word we get 
**ANSWER: Area51**

Who is the other agent (in full name)?

Now that we have the steg passphrase lets see whats in the file

![Screenshot 2025-08-20 at 12.15.41 PM.png](images/11-screenshot.png)

![Screenshot 2025-08-20 at 12.17.05 PM.png](images/12-screenshot.png)

---

# Task 4: Capture the user flag

You know the drill.

What is the user flag?

![Screenshot 2025-08-20 at 12.20.58 PM.png](images/13-screenshot.png)

**ANSWER: b03d975e8c92a7c04146cfa7a5a313c7**

What is the incident of the photo called?

I used tineye to do a reverse image search and got the “**Roswell alien autopsy”**

![Screenshot 2025-08-20 at 12.29.11 PM.png](images/14-screenshot.png)

---

# Task 5: Privilege escalation

Enough with the extraordinary stuff? Time to get real.

CVE number for the escalation

(Format: CVE-xxxx-xxxx)

We list what james is able to sudo by using ‘sudo -l’

![Screenshot 2025-08-20 at 12.38.57 PM.png](images/15-screenshot.png)

we do a quick google search “CVE (ALL, !root) /bin/bash” and we get the CVE

**ANSWER: CVE-2019-14287**

What is the root flag?

![Screenshot 2025-08-20 at 12.47.35 PM.png](images/16-screenshot.png)

![Screenshot 2025-08-20 at 12.50.53 PM.png](images/17-screenshot.png)
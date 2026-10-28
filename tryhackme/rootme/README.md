# RootMe


A ctf for beginners, can you root me?

---

# Task 1: Deploy the machine

Connect to TryHackMe network and deploy the machine. If you don't know how to do this, complete the [OpenVPN room](https://tryhackme.com/room/openvpn) first.

![Screenshot 2025-08-18 at 3.42.07 PM.png](images/01-screenshot.png)

---

# Task 2: Reconnaissance

First, let's get information about the target.

Scan the machine, how many ports are open?

![Screenshot 2025-08-18 at 3.58.48 PM.png](images/02-screenshot.png)

**ANSWER: 2**

What version of Apache is running?

**ANSWER: 2.4.29 (but current apache server is .41)**

What service is running on port 22?

**ANSWER: ssh**

Find directories on the web server using the GoBuster tool.

For this i use the —no-error because i know its a ctf so usually errors are not important

![Screenshot 2025-08-18 at 4.18.13 PM.png](images/03-screenshot.png)

**ANSWER: /panel/** 

---

# Task 3: Getting a shell

Find a form to upload and get a reverse shell, and find the flag.

![Screenshot 2025-08-18 at 5.04.17 PM.png](images/04-screenshot.png)

we had to make sure the php file ended in .php5 because .php was blocked

![Screenshot 2025-08-18 at 5.03.28 PM.png](images/05-screenshot.png)

![Screenshot 2025-08-18 at 5.06.45 PM.png](images/06-screenshot.png)

---

# Task 4: Privilege escalation

Now that we have a shell, let's escalate our privileges to root.

Search for files with SUID permission, which file is weird?

```bash
find / -user root -perm /4000
```

![Screenshot 2025-08-18 at 5.16.34 PM.png](images/07-screenshot.png)

There’s many way to escalate but the CTF is pointing to using python in order to stabilize. 

```bash
python -c 'import pty; pty.spawn("/bin/bash")'
```

Now to see how we can escalate. We go into gtfobins and search for suid on python

![Screenshot 2025-08-18 at 5.22.47 PM.png](images/08-screenshot.png)

![Screenshot 2025-08-18 at 5.27.02 PM.png](images/09-screenshot.png)
# Wgel CTF


Description:

Can you exfiltrate the root flag?

---

# User flag

First we enumerate to se what ports are open.

![Screenshot 2025-08-20 at 1.02.51 PM.png](images/01-screenshot.png)

We tried to go into the website and its just the starter apache page so lets see if doing a directory search might work out. While the gobuster dir search is going  decided to look at the page source and theres a possible username <u>Jessie</u>

![Screenshot 2025-08-20 at 6.35.38 PM.png](images/02-screenshot.png)

We got something, but once we take a look its actually not much so lets dir /sitemap

![Screenshot 2025-08-20 at 6.37.50 PM.png](images/03-screenshot.png)

Interesting we got a /.ssh so lets take a look

![Screenshot 2025-08-20 at 6.40.08 PM.png](images/04-screenshot.png)

And we got a id_rsa. Nice lets ssh into jessie with this rsa

![Screenshot 2025-08-20 at 6.41.02 PM.png](images/05-screenshot.png)

We copied the rsa key and chmod it to 600 and boom, we got access.

![Screenshot 2025-08-20 at 6.43.32 PM.png](images/06-screenshot.png)

![Screenshot 2025-08-20 at 6.47.16 PM.png](images/07-screenshot.png)

**ANSWER: 057c67131c3d5e42dd5cd3075b198ff6**

---

# Root flag

In order to escalate we need to see what we can use. So before we enumerate lets check sudo -l

![Screenshot 2025-08-20 at 6.47.53 PM.png](images/08-screenshot.png)
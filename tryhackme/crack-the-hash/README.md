# Crack the hash


Description:

Cracking hashes challenges

---

# Task 1: Level 1

Can you complete the level 1 tasks by cracking the hashes?

![Screenshot 2025-08-20 at 7.19.27 PM.png](images/01-screenshot.png)

we copied the hashes into CrackStation

![Screenshot 2025-08-20 at 7.19.57 PM.png](images/02-screenshot.png)

All of these where easy except the $2y$. We looked at the hashcat example and we found what type it is.

| 3200 | bcrypt $2*$, Blowfish (Unix) | $2a$05$LhayLxezLhK1LhWvKxCyLOj0j1u.Kj0jZ0pEmm134uzrQlFvQJLF6 |
| --- | --- | --- |

Which this takes really long so instead of using the whole rockyou.txt we first got only the 4 character long words, because tryhackme hints at it with the ****.

```bash
grep -x '.\{4\}' /usr/share/wordlists/rockyou.txt > rockyou-4.txt
```

![Screenshot 2025-08-20 at 7.48.57 PM.png](images/03-screenshot.png)

---

# Task: Level 2

First two hashes are simple.

![Screenshot 2025-08-20 at 7.50.35 PM.png](images/04-screenshot.png)

For the last hash we also found it easy on [hashes.com](http://hashes.com), lets work on the only hash left.

![Screenshot 2025-08-20 at 8.00.07 PM.png](images/05-screenshot.png)

This in hashcat is 1800 so let run hashcat and wait

![Screenshot 2025-08-20 at 8.01.17 PM.png](images/06-screenshot.png)

```bash
 hashcat -m 1800 -a 0 hash2.txt /usr/share/wordlists/rockyou.txt
```

![Screenshot 2025-08-20 at 8.42.40 PM.png](images/07-screenshot.png)
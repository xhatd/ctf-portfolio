# LazyAdmin

**Platform:** TryHackMe
**Difficulty:** Easy
**Status:** Completed
**Completed:** May 7, 2026

## Reconnaissance

We start with an Nmap scan.

![Nmap Scan](images/01-nmap.png)

We don't find anything useful on the website, so we continue with a Gobuster directory search. We only find one directory: `/content`.

![Gobuster](images/02-gobuster.png)

Let's run Gobuster against `/content/` and, while we wait, look for SweetRice CVEs and exploits.

We find several exploits, and Gobuster discovers additional directories.

![SweetRice](images/03-sweetrice.png)

After manually examining the directories and reading the exploits, we discover `/inc/mysql_backup`.

![MySQL Backup](images/04-mysql-backup.png)

I'm using a VM, so I'll download the MySQL backup file using `wget` to inspect it and keep it for my notes.

```bash
wget http://<TARGET_IP>/content/inc/mysql_backup/mysql_bakup_20191129023059-1.5.1.sql
```

We can use `cat`, or in my case Vim, to search the file for sensitive information.

![Inspecting SQL](images/05-sql.png)

We find a serialized password field containing a 32-character hash consistent with MD5.

- `passwd` — The field containing the password hash.
- `s:32` — The serialized string length is 32 characters.
- The hash can be checked against a password-cracking database.

We use CrackStation to look up the hash and recover the password.

![CrackStation](images/06-crackstation.png)

Right before the password field, we also find `manager`, which looks like the username.

![Username](images/07-username.png)

## Getting a Shell

We're able to log into the dashboard and discover that the Media Center allows file uploads.

Let's create a reverse shell and see what we can find.

![Dashboard](images/08-dashboard.png)

We upload the file, start a Netcat listener, and open the uploaded file's link.

![Reverse Shell](images/09-reverse-shell.png)

Let's improve our shell and look around.

```bash
python -c 'import pty; pty.spawn("/bin/bash")'
```

![User Flag](images/10-user-flag.png)

Boom! We found our first flag.

We also find a `mysql_login` file containing database login information, which we can investigate.

![MySQL Credentials](images/11-mysql.png)

## Privilege Escalation

Let's run `sudo -l`, which I almost forgot.

```bash
sudo -l
```

![Sudo Permissions](images/12-sudo.png)

Let's investigate `backup.pl`.

![Backup Script](images/13-backup.png)

It looks like a reverse shell, so let's modify the IP address and open a Netcat listener on port `5554`.

![Modified Backup](images/14-modified-backup.png)

It took a while to connect. I was checking whether I'd written the `echo` command correctly when the connection finally appeared!

![Root Shell](images/15-root-shell.png)

We got the root flag!


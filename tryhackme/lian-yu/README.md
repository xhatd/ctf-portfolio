# Lian_Yu


A beginner level security challenge

---

# Task 1: Find the Flags

![Screenshot 2025-08-01 at 10.52.01 AM.png](images/01-screenshot.png)

We deployed the VM and now we run nmap to see what ports are open.

 

```bash
 nmap -sC -sV -p- 10.201.97.60 -oN scan.txt
```

![Screenshot 2025-08-01 at 11.28.28 AM.png](images/02-screenshot.png)

mmhh lets take a look at the website.

![Screenshot 2025-08-01 at 11.40.23 AM.png](images/03-screenshot.png)

Not much to see here, so I took a look at the source code and got nothing. Lets run a directory search using gobuster. The next part of the task ask what web dir we found so i think we are in the right track

![Screenshot 2025-08-01 at 11.41.55 AM.png](images/04-screenshot.png)

```bash
gobuster dir -u http://10.201.97.60 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt --no-error
```

![Screenshot 2025-08-01 at 11.47.28 AM.png](images/05-screenshot.png)

Nice we got one, lets take a look while the scan keeps going.

![Screenshot 2025-08-01 at 11.48.08 AM.png](images/06-screenshot.png)

One of the oldest tric is to hide it and we can see if we highlight it

![Screenshot 2025-08-01 at 11.48.35 AM.png](images/07-screenshot.png)

We didnt find much other than server side. So lets try gobuster on the /island 

![Screenshot 2025-08-01 at 12.38.44 PM.png](images/08-screenshot.png)

Lets look at the webpage, i’m not sure if this is supposed to be like this so lets run another gobuster on /island/2100 maybe we can get something on this page.

![Screenshot 2025-08-01 at 12.40.11 PM.png](images/09-screenshot.png)

The source page talks about a .ticket so lets google and see if we get something.

![Screenshot 2025-08-01 at 10.07.36 PM.png](images/10-screenshot.png)

I didn’t find anything so lets use the -x flag on gobuster o search for an extension with the .ticket

![Screenshot 2025-08-01 at 10.21.33 PM.png](images/11-screenshot.png)

We got this which i think this might be a encoded password. Lets throw this on cyberchef magic to see if we get something

![Screenshot 2025-08-01 at 10.23.00 PM.png](images/12-screenshot.png)

I didnt get much on the magic option but a lead that its encoded from a base. Let try to ftp using vigilante from before as the username and one of these will be our password. once i tried base58 i got !#th3h00d which is a reference to the green arrow.

![Screenshot 2025-08-01 at 10.29.18 PM.png](images/13-screenshot.png)

![Screenshot 2025-08-01 at 10.34.12 PM.png](images/14-screenshot.png)

Now lets see whats in the pictures. Leave_me_alone.png wont open lets see if we can fix it with hexedit.

![Screenshot 2025-08-01 at 10.40.11 PM.png](images/15-screenshot.png)

mmmhhh I’m not a genius so lets look in google how a png signature should look like.

> A PNG file header, also known as a signature, consists of the first 8 bytes of the file and is always `89 50 4E 47 0D 0A 1A 0A` in hexadecimal. This sequence identifies the file as a PNG and is crucial for applications to correctly interpret the file format. Beyond the header, PNG files contain chunks of data, including the [IHDR chunk](https://www.google.com/search?client=firefox-b-1-d&cs=1&sca_esv=f3a7ee0e23e81309&sxsrf=AE3TifMb1z8nrIgmjfN0gyF3vieR7mO-ww%3A1754102464208&q=IHDR+chunk&sa=X&ved=2ahUKEwj4qPHxjOuOAxXbFVkFHVuTFrAQxccNegQIBxAB&mstk=AUtExfA3_OopgBAjtRIMK8igIyL0rcXfSdDlJGBX7GOPnPCglX1Z49ZoUspY9cbFdO4sDAfc_JJzPw5R6HtqTtFbD5GOfXV6G1m6QEaYie3qkg2WlcVRPblBJLVKDO68F-w2cLSrkfodGqevWV06RWchEl8x04rUnrL_jMisZM6srJTj1JHKWgNEdeyeOPoaxwF6eix59_sCu-khhyM0s-kLCvZwBq4w2LPUV9NOwVl5cd3w4K60i1ZyXKqlLBmYAZxkTHdxOvZFqmjiH99xyDP_yWCi&csui=3) which specifies image dimensions.
> 

We changed it and to save and exit we use Ctrl-x. 

![Screenshot 2025-08-01 at 10.50.52 PM.png](images/16-screenshot.png)

now we have a password, but for what? First thing that i cant think is steg. Since we go 3 picture lets start with the .jpg since its the most common in steg.

![Screenshot 2025-08-01 at 10.56.23 PM.png](images/17-screenshot.png)

Nice!! Lets unzip and see what’s in there. Two files and one has the ssh of the other account we found while we ftpd into vigilante.

![Screenshot 2025-08-01 at 10.59.06 PM.png](images/18-screenshot.png)

Lest ssh into the machine.

![Screenshot 2025-08-01 at 11.00.33 PM.png](images/19-screenshot.png)

Lets go!!!

![Screenshot 2025-08-01 at 11.01.15 PM.png](images/20-screenshot.png)

and we got the user flag. Now lets get the root flag. Use sudo -l to list what we can run as root.

![Screenshot 2025-08-01 at 11.05.19 PM.png](images/21-screenshot.png)

I’m learning as we go through this CTF and so lets google what pkexec is

> The primary purpose of `pkexec` is to allow authorized users to run programs as another user, usually the super-administrator (root). This is particularly useful in environments where users may not have direct root access but require it for specific administrative tasks.
> 

so we should be able to run a /bin/bash shell to get root

![Screenshot 2025-08-01 at 11.13.05 PM.png](images/22-screenshot.png)
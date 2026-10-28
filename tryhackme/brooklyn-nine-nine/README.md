# Brooklyn Nine Nine


![Screenshot 2025-10-08 at 2.44.10 PM.png](images/01-screenshot.png)

We see that ftp is available to login as anonymous, so lets go take a look and see what we got

![Screenshot 2025-10-08 at 2.45.16 PM.png](images/02-screenshot.png)

Now lets cat the file

> *From Amy,*
> 
> 
> *Jake please change your password. It is too weak and holt will be mad if someone hacks into the nine nine*
> 

Which most likely means ‘jake’ is the username so lets use hydra to bruteforce the password

![Screenshot 2025-10-08 at 4.39.01 PM.png](images/03-screenshot.png)

Now that we have the username and password lets login and see what files we can find

![Screenshot 2025-10-08 at 4.45.51 PM.png](images/04-screenshot.png)

Now we got the first flag. Now we have to try to get root flag. In order to do that lets see if we are able to run anything with sudo.

![Screenshot 2025-10-09 at 5.22.41 PM.png](images/05-screenshot.png)

We see that /usr/bin/less has sudo permission so we go into gtfobins and see privilege escalation [https://gtfobins.github.io/gtfobins/less/#sudo](https://gtfobins.github.io/gtfobins/less/#sudo)

![Screenshot 2025-10-09 at 5.24.35 PM.png](images/06-screenshot.png)
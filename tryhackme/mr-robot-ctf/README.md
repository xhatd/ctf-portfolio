# Mr Robot CTF


Description:

Based on the Mr. Robot show, can you root this box?

---

![](https://i.imgur.com/mp5JwKO.png)

Can you root this Mr. Robot styled machine? This is a virtual machine meant for beginners/intermediate users. There are 3 hidden keys located on  the machine, can you find them?

Credit to [Leon Johnson](https://twitter.com/@sho_luv) for creating this machine. **This machine is used here with the explicit permission of the creator <3**

First we run an nmap of our machine and we get that every port is closed

![Screenshot 2025-08-20 at 9.14.22 PM.png](images/01-screenshot.png)

So we look at the first hint and it says

> Robots
> 

So we take a look at the robots.txt 

![Screenshot 2025-08-20 at 9.15.18 PM.png](images/02-screenshot.png)

**ANSWER:** `073403c8a58a1f80d943455fb30724b9`

---

mmmmhh Interesting on the .dic file lets save it either with curl or save as a .txt file directly with firefox. Lets use gobuster dir with the file we got.

![Screenshot 2025-08-21 at 11.08.32 PM.png](images/03-screenshot.png)

Lets take a look at /license.

![Screenshot 2025-08-21 at 11.11.19 PM.png](images/04-screenshot.png)

We get this `ZWxsaW90OkVSMjgtMDY1Mgo=` which loks like base64 so lets go to our friend cyberchef. We get this elliot:ER28-0652. First lets try it as a login on the /login page.
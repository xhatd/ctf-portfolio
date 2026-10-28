# PW Crack 4


Author: LT 'syreal' Jones

### Description

Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/19/level4.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/19/level4.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/19/level4.hash.bin) in the same directory too. There are 100 potential passwords with only 1 being correct. You can find these by examining the password checker script.

---

First we get the 3 files into our VM and to see what we are dealing with.

![Screenshot 2025-07-30 at 9.00.22 PM.png](images/01-screenshot.png)

The solution i came up with was using a loop to bruteforce.

![Screenshot 2025-07-30 at 9.16.22 PM.png](images/02-screenshot.png)

Now we run the program we get the password.

![Screenshot 2025-07-30 at 9.13.56 PM.png](images/03-screenshot.png)
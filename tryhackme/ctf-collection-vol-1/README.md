# CTF collection Vol.1


# Task 1: Author notes

Just another random CTF room created by me. Well, the main objective of the room is to test your CTF skills. For your information, vol.1 consists of 20 tasks and all the challenges are extremely easy. Stay calm and Capture the flag. :)

Note: All the challenges flag are formatted as `THM{flag}`, unless stated otherwise

![Screenshot 2025-10-09 at 5.37.04 PM.png](images/01-screenshot.png)

---

# Task 2: What does the base said?

Can you decode the following?

VEhNe2p1NTdfZDNjMGQzXzdoM19iNDUzfQ==

Since it has == in the end it a type of base encryption and we tried base64 first which it turned out to be correct 

![Screenshot 2025-10-09 at 5.39.47 PM.png](images/02-screenshot.png)

---

# Task 3: Meta meta

Meta! meta! meta! meta................................…

For this im guessing it need to use exiftool

![Screenshot 2025-10-09 at 5.47.18 PM.png](images/03-screenshot.png)

![Screenshot 2025-10-09 at 5.47.46 PM.png](images/04-screenshot.png)

---

# Task 4: Mon, are we going to be okay?

Something is hiding. That's all you need to know.

For this challenge we use steghide without a passphrase.

![Screenshot 2025-10-09 at 6.05.05 PM.png](images/05-screenshot.png)

![Screenshot 2025-10-09 at 6.06.49 PM.png](images/06-screenshot.png)

---

# Task 5: Erm......Magick

![Screenshot 2025-10-09 at 6.07.47 PM.png](images/07-screenshot.png)

All you have to do is highlight and you will get the ctf

![Screenshot 2025-10-09 at 6.08.34 PM.png](images/08-screenshot.png)

---

# Task 6: QRrrrr

Such technology is quite reliable.

I used a online QR scanner for this one and the flag was there.

![Screenshot 2025-10-09 at 6.13.27 PM.png](images/09-screenshot.png)

![Screenshot 2025-10-09 at 6.14.42 PM.png](images/10-screenshot.png)

---

# Task 7: Reverse it or read it?

Both works, it's all up to you.

I dont have a way to open it because I download it from my mac and then scp into my linux so i get some errors if i try to run it as an exec. So, I just use vim and /THM to find the flag.

![Screenshot 2025-10-09 at 6.23.29 PM.png](images/11-screenshot.png)

![Screenshot 2025-10-09 at 6.25.33 PM.png](images/12-screenshot.png)

---

# Task 8: Another decoding stuff

Can you decode it?

3agrSy1CewF9v8ukcSkPSYm3oKUoByUpKG4L

cyberchef has a magic option which makes decoding easy

![Screenshot 2025-10-10 at 12.30.56 PM.png](images/13-screenshot.png)

![Screenshot 2025-10-10 at 12.31.12 PM.png](images/14-screenshot.png)

---

# Task 9: Left or right

Left, right, left, right... Rot 13 is too mainstream. Solve this

MAF{atbe_max_vtxltk}

We use cyberchef ROT option and it turne out to be ROT7

![Screenshot 2025-10-10 at 12.32.49 PM.png](images/15-screenshot.png)

---

# Task 10: Make a comment

No downloadable file, no ciphered or encoded text. Huh ....…

Mmmhh this might look like i need to look at the html to see for a comment.

![Screenshot 2025-10-10 at 12.37.55 PM.png](images/16-screenshot.png)

---

# Task 11: Can you fix it?

I accidentally messed up with this PNG file. Can you help me fix it? Thanks, ^^ 

This has to do with the header of the image. So we use hexedit and search png header.

![spoil_1577979329740.png](images/17-screenshot.png)

![Screenshot 2025-10-10 at 12.47.05 PM.png](images/18-screenshot.png)

---

# Task 12: Read it

Some hidden flag inside Tryhackme social account.

Lets use google to find tryhackme social and see if they have a flag. This one was hard to find since this is 6ish year old room but while looking at reddit heres the link.
[https://www.reddit.com/r/tryhackme/comments/eizxaq/new_room_coming_soon/](https://www.reddit.com/r/tryhackme/comments/eizxaq/new_room_coming_soon/)

![Screenshot 2025-10-10 at 12.54.47 PM.png](images/19-screenshot.png)

---

# Task 13: Spin my head

What is this?

++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>++++++++++++++.------------.+++++.>+++++++++++++++++++++++.<<++++++++++++++++++.>>-------------------.---------.++++++++++++++.++++++++++++.<++++++++++++++++++.+++++++++.<+++.+.>----.>++++.

This is some binary shit. Its called binaryfuck 

![Screenshot 2025-10-10 at 1.09.07 PM.png](images/20-screenshot.png)

---

# Task 14: An exclusive!

Exclusive strings for everyone!

S1: 44585d6b2368737c65252166234f20626d
S2: 1010101010101010101010101010101010

This one is a weird one. From the Exclusive i think of XOR but how to decode this might be tricky and got me good. I use cyberchef and put the S1 as the input and the S2 as the key on the XOR. but i would get this none sense. So trying and getting it wrong i though maybe it needs another decode before. Since their is letters and number this means its hexadecimal which then we got it.

![Screenshot 2025-10-11 at 11.19.15 AM.png](images/21-screenshot.png)

---

# Task 15: Binary walk

Please exfiltrate my file :)

The title is binary walk and the hint is exfiltrate, which makes me think of binwalk

![Screenshot 2025-10-11 at 11.25.17 AM.png](images/22-screenshot.png)

Then we use the -e flag to extract

![Screenshot 2025-10-11 at 11.27.15 AM.png](images/23-screenshot.png)

![Screenshot 2025-10-11 at 11.27.53 AM.png](images/24-screenshot.png)

---

# Task 16: Darkness

There is something lurking in the dark.

I havent done many steg with color bits but this was hinting to use stegsolve. Before installing i always try to look at the manual and if its a tool that is being maintained, which it wasnt so i used a tool online [https://georgeom.net/StegOnline/image](https://georgeom.net/StegOnline/image) . I started playing with all the buttons and once i got to messing with the color it showed a flag.

![Screenshot 2025-10-11 at 11.57.08 AM.png](images/25-screenshot.png)

---

# Task 17: A sounding QR

How good is your listening skill?

P/S: The flag formatted as THM{Listened Flag}, the flag should be in All CAPS

![Screenshot 2025-10-11 at 2.53.27 PM.png](images/26-screenshot.png)

---

# Task 18: Dig up the past

Sometimes we need a 'machine' to dig the past

Targetted website: https://www.embeddedhacker.com/

Targetted time: 2 January 2020

Use the wayback machine.

![Screenshot 2025-10-11 at 3.03.46 PM.png](images/27-screenshot.png)

---

# Task 19: Uncrackable!

Can you solve the following? By the way, I lost the key. Sorry >.<

MYKAHODTQ{RVG_YVGGK_FAL_WXF}

Flag format: TRYHACKME{FLAG IN ALL CAP}

For this one i used the hint, i knew it was a type of cipher but i wasnt aware of vigenere. Once i saw i started playing with the key and wrote tryhackme and saw that the output was THMTHMTPE{YEI_RVEWG_THU_YQF} so i tried thm and got the flag.

![Screenshot 2025-10-11 at 3.12.20 PM.png](images/28-screenshot.png)

![Screenshot 2025-10-11 at 3.15.57 PM.png](images/29-screenshot.png)

---

# Task 20: Small bases

Decode the following text.

581695969015253365094191591547859387620042736036246486373595515576333693

![Screenshot 2025-10-11 at 3.30.02 PM.png](images/30-screenshot.png)

---

# Task 21:
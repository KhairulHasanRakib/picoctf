# 1

**Forensics
Verify**

**Answer: picoCTF{trust_but_verify_87590c24}**

Author: Jeffery John
Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
Additional details will be available after launching your challenge instance.

People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.

ssh -p 60760 ctf-player@rhea.picoctf.net
password f3b61b38

Using the password f3b61b38. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!

Checksum: fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7
To decrypt the file once you've verified the hash, run ./decrypt.sh files/`<file>`.

Answer:

1. Open picoCTF Webshell
2. Copy "ssh -p 60760 ctf-player@rhea.picoctf.net" and past
3. Password: "f3b61b38" and enter.
4. ls
5. cat checksum.txt (and remember it)

Manually check:
6. cd files
7. ls
8. sha256sum 87590c24 (same process for all until match checksum.txt output)
7. cd ..
8. ./decrypt.sh files/87590c24 (when match with checksum.txt)

Automatically check:
9. for file in files/*; do sha256sum "$file" | grep -q 'fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7' && echo "Valid flag found: $file"; done
10. ./decrypt.sh files/87590c24 (enter then get flag)
11. picoCTF{trust_but_verify_87590c24} (this is the answer of the flag)

# 2

Forensics
Scan Surprise

Author: Jeffery John

Description
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
You can download the challenge files here:
challenge.zip (https://artifacts.picoctf.net/c_atlas/16/challenge.zip)
Additional details will be available after launching your challenge instance.

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
You can download the challenge files here:
challenge.zip
The same files are accessible via SSH here:
ssh -p 62096 ctf-player@atlas.picoctf.net
Using the password 6abf4a82. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!

Answer:

1. Download challenge.zip
2. Open and scan qr code
3. Get answer. picoCTF{p33k_@_b00_7843f77c}

or

1. Run picoCTF Webshell
2. ssh -p 62096 ctf-player@atlas.picoctf.net
3. 6abf4a82
4. Scan qr code then get answer. picoCTF{p33k_@_b00_7843f77c}

or

5. zbarimg flag.png
6. picoCTF{p33k_@_b00_7843f77c}

# 3

General Skills
Binary Search

Author: Jeffery John

Description
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.
Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!
You can download the challenge files here:
challenge.zip (https://artifacts.picoctf.net/c_atlas/5/challenge.zip)
Additional details will be available after launching your challenge instance.

ssh -p 56235 ctf-player@atlas.picoctf.net
Using the password 1ad5be0d. Accept the fingerprint with yes, and ls once connected to begin. Remember, in a shell, passwords are hidden!

Answer:
Guess: 207 (for me)
picoCTF{g00d_gu355_3af33d18}

1. download zip
2. run bash file in terminal "./file.sh"
3. guess your number (207 for me)
4. get flag "picoCTF{g00d_gu355_3af33d18}"

or

open webshell then connect ssh with pass then auto run file.sh. just guess your number then boom your answer.

# 4

# Binary Exploitation

heap 0

Author: Abrxs, pr1or1tyQ

Description
Are overflows just a stack concern?
Download the binary here (https://artifacts.picoctf.net/c_tethys/15/chall).
Download the source here (https://artifacts.picoctf.net/c_tethys/15/chall.c).
Additional details will be available after launching your challenge instance.

Connect with the challenge instance here:
nc tethys.picoctf.net 64643

Answer:

1. open webshell
2. connect nc (nc tethys.picoctf.net 64643)
3. see heap
4. download source code
5. analyze code (here showing buffer overflow function. if input data more than 5 bytes then it's cracked. then you can print the flag)
6. print 2 for input buffer.
7. write anything must be more than 10/15 character for buffer overflow.
8. again print heap and see the changes.
9. finally print 4 for see flag "picoCTF{my_first_heap_overflow_0c473fe8}"

Your flag might be looking like this.

# 5

Format String

Author: Cheng Zhang

Description
Can you use your knowledge of format strings to make the customers happy?
Download the binary here. (https://artifacts.picoctf.net/c_mimas/69/format-string-0)
Download the source here. (https://artifacts.picoctf.net/c_mimas/69/format-string-0.c)
Additional details will be available after launching your challenge instance.

Connect with the challenge instance here:
nc mimas.picoctf.net 49634

Answer:

1. open shell
2. connect server
3. read source code and understand (user input available and if input overflow 2 * BUFSIZE then server destroy.
4. input very long string for buffer overflow
5. get flag like (picoCTF{7h3_cu570m3r_15_n3v3r_SEGFAULT_dc0f36c4})

Flag is: picoCTF{7h3_cu570m3r_15_n3v3r_SEGFAULT_dc0f36c4}

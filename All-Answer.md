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

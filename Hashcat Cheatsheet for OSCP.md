Hashcat Cheatsheet for OSCP
Identify Hashes
1. Use hash-identifier:
bash
Copy code
hash-identifier
Description:
Identify hash types using hash-identifier tool.
MAX POWER!
2. Optimize for Maximum Performance:
bash
Copy code
hashcat --force -O -w 4 --opencl-device-types 1,2
Description:
Optimize Hashcat for maximum performance using CUDA GPU interface.
--force: Force Hashcat to use CUDA GPU.
-O: Optimize for 32 characters or less passwords.
-w 4: Set workload to "Insane."
--opencl-device-types 1,2: Use both GPU and CPU.
Using hashcat and a Dictionary
3. Cracking Linux md5crypt Passwords using rockyou:
bash
Copy code
hashcat --force -m 500 -a 0 -o found1.txt --remove puthasheshere.hash /usr/share/wordlists/rockyou.txt
Description:
Crack Linux md5crypt passwords using Hashcat and rockyou dictionary.
Parameters:
--force: Force Hashcat to use the chosen attack mode.
-m 500: Specify the hash type (Linux md5crypt).
-a 0: Use straight (dictionary) attack.
-o found1.txt: Output file for cracked passwords.
--remove: Remove hash once it is cracked.
puthasheshere.hash: Replace with the path to your hash file.
/usr/share/wordlists/rockyou.txt: Path to rockyou dictionary.
4. Cracking Wordpress Passwords using rockyou:
bash
Copy code
hashcat --force -m 400 -a 0 -o found1.txt --remove wphash.hash /usr/share/wordlists/rockyou.txt
Description:
Crack Wordpress passwords using Hashcat and rockyou dictionary.
Parameters:
Similar to the Linux md5crypt example.
HashCat One Rule to Rule them All
5. Using the Not So Secure Rule:
bash
Copy code
hashcat64.exe --force -m300 --status -w3 -o found.txt --remove --potfile-disable -r rules\OneRuleToRuleThemAll.rule hash.txt rockyou.txt
Description:
Use the "One Rule to Rule Them All" rule from Not So Secure.
Parameters:
--force: Force Hashcat to use the chosen attack mode.
-m300: Specify the hash type.
-r rules\OneRuleToRuleThemAll.rule: Path to the custom rule.
hash.txt: Replace with the path to your hash file.
rockyou.txt: Path to rockyou dictionary.
Using hashcat Brute Forcing
6. Brute Force all Passwords Length 1-8:
bash
Copy code
hashcat64 -m 500 hashes.txt -a 3 ?1?1?1?1?1?1?1?1 --increment -1 ?l?d?u
Description:
Brute force all passwords with lengths 1-8 using hashcat.
Parameters:
-m 500: Specify the hash type.
-a 3: Use brute-force attack mode.
hashes.txt: Replace with the path to your hash file.
--increment -1 ?l?d?u: Brute force characters A-Z a-z 0-9.
Cracking Linux Hashes (/etc/shadow file)
7. Cracking Linux Hashes:
bash
Copy code
hashcat64 -m 500 hashes.txt -a 0 /usr/share/wordlists/rockyou.txt
Description:
Crack Linux password hashes from /etc/shadow file using hashcat.
Parameters:
-m 500: Specify the hash type.
-a 0: Use straight (dictionary) attack.
hashes.txt: Replace with the path to your hash file.
/usr/share/wordlists/rockyou.txt: Path to rockyou dictionary.
Cracking Windows Hashes
8. Cracking Windows NTLM Hashes:
bash
Copy code
hashcat64 -m 1000 -a 0 -w 4 --force --opencl-device-types 1,2 -O d:\hashsample.hash "d:\WORDLISTS\realuniq.lst" -r OneRuleToRuleThemAll.rule
Description:
Crack Windows NTLM hashes using hashcat.
Parameters:
Similar to the Linux md5crypt example.
Cracking Common Hash Formats
9. Cracking Common Hash Formats:
Refer to the Hashcat Wiki for specific examples: Hashcat Wiki - Hash Modes

Cracking Common File Password Protections
10. Cracking Common File Password Protections:
Refer to the Hashcat Wiki for specific examples: Hashcat Wiki - Hash Modes

Cracking Common Database Hash Formats
11. Cracking Common Database Hash Formats:
Refer to the Hashcat Wiki for specific examples: Hashcat Wiki - Hash Modes

Cracking NTLM Hashes from a Packet Capture
12. Cracking NTLM Hashes from a Packet Capture:
Refer to the Hashcat Wiki for specific examples: Hashcat Wiki - NTLMv1 and NTLMv2

Cracking Hashes from Kerberoasting - KRB5TGS
13. Cracking KRB5TGS Hashes:
Refer to the Hashcat Wiki for specific examples: Hashcat Wiki - KRB5TGS

Cracking NTLMv2 Hashes from a Packet Capture
14. Cracking NTLMv2 Hashes from a Packet Capture:
Refer to the Hashcat Wiki for specific examples: Hashcat Wiki - NTLMv1 and NTLMv2

Unshadowing Linux Password Files
15. Unshadowing Linux Password Files:
bash
Copy code
unshadow passwd-file.txt shadow-file.txt > unshadowed.txt
Description:
Unshadow Linux password files before cracking.
Cracking a Zip Password
16. Cracking a Zip Password:
bash
Copy code
zip2john Zipfile.zip | cut -d ':' -f 2 > hashes.txt
hashcat -a 0 -m 13600 hashes.txt /usr/share/wordlists/rockyou.txt
Description:
Crack a Zip file password using hashcat.
PRINCE Password Generation
17. PRINCE Password Generation:
bash
Copy code
pp64.bin --pw-min=8 < dict.txt | head -20
shuf dict.txt | pp64.bin --pw-min=8 | head -20
Description:
Generate probable passwords using PRINCE.
Parameters:
--pw-min=8: Specify minimum password length.
Purple Rain Attack
18. Purple Rain Attack:
bash
Copy code
shuf dict.txt | pp64.bin --pw-min=8 | hashcat -a 0 -m #type -w 4 -O hashes.txt -g 300000
Description:
Perform a Purple Rain attack using Hashcat and PRINCE.
This guide provides step-by-step instructions for using Hashcat in various scenarios. Customize the parameters based on your specific requirements and ensure compliance with legal and ethical standards.






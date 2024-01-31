masscan on Kali Linux
1. Install masscan:
bash
Copy code
sudo apt update
sudo apt install masscan
2. Scan IP Range for Open Ports:
Replace target_range with the IP range you want to scan.

bash
Copy code
sudo masscan -p1-65535 target_range
3. Output Results to File:
Specify an output file for the scan results.

bash
Copy code
sudo masscan -p1-65535 target_range -oL scan_results.txt
4. Scan Specific Ports:
Replace ports with the specific ports you want to scan.

bash
Copy code
sudo masscan -p ports target_range
nmap on Kali Linux
1. Install nmap:
bash
Copy code
sudo apt update
sudo apt install nmap
2. Basic Scan:
Replace target_ip with the IP address you want to scan.

bash
Copy code
nmap target_ip
3. Service Version Detection:
bash
Copy code
nmap -sV target_ip
4. Operating System Detection:
bash
Copy code
nmap -O target_ip
5. Scan Specific Ports:
Replace ports with the specific ports you want to scan.

bash
Copy code
nmap -p ports target_ip
6. Aggressive Scan:
bash
Copy code
nmap -A target_ip
7. Output Results to File:
Specify an output file for the scan results.

bash
Copy code
nmap target_ip -oN scan_results.txt
8. Scan Multiple Targets:
Replace target_ips with a list of IP addresses.

bash
Copy code
nmap target_ip1 target_ip2
9. Exclude Hosts from Scan:
Replace excluded_ip with the IP address to exclude.

bash
Copy code
nmap target_ip --exclude excluded_ip
10. Perform a SYN Stealth Scan:
bash
Copy code
nmap -sS target_ip
This guide provides specific instructions for installing and using masscan and nmap on Kali Linux. Customize the commands based on your specific requirements, and ensure you have proper authorization before performing any network scanning or testing.
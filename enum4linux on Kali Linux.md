enum4linux on Kali Linux
1. Open a Terminal:
Open a terminal on your Kali Linux system. You can usually find the terminal in the applications menu or use the shortcut Ctrl + Alt + T.
2. Install enum4linux:
enum4linux is pre-installed on Kali Linux. However, you can ensure you have the latest version by updating your system:

bash
Copy code
sudo apt update
sudo apt upgrade enum4linux
3. Run enum4linux:
To use enum4linux on a target, run the following command:

bash
Copy code
enum4linux <target_IP>
Replace <target_IP> with the IP address of the target machine.

4. Specify Additional Options:
enum4linux supports various options for more detailed enumeration. For example:

bash
Copy code
enum4linux -a <target_IP>
The -a option enables all scanning options.

5. Specify a Range of IPs:
If you want to scan a range of IP addresses, you can use:

bash
Copy code
enum4linux -r <start_IP>-<end_IP>
Replace <start_IP> and <end_IP> with the range of IP addresses.

6. Output Results to a File:
To save the results to a file, you can use the following command:

bash
Copy code
enum4linux <target_IP> > results.txt
This will save the output to a file named results.txt.

7. Review Output:
After running enum4linux, review the output for information about the target Windows/Samba domain.
Note:
Ensure that you have proper authorization before using enum4linux on any network or system.
enum4linux is a tool for information gathering and should be used responsibly and within legal and ethical boundaries.
This guide provides instructions for using enum4linux on Kali Linux.
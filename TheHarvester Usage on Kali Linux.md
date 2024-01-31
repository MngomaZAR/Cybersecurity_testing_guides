TheHarvester Usage on Kali Linux
1. Open a Terminal:
Open a terminal on your Kali Linux system. You can usually find the terminal in the applications menu or use the shortcut Ctrl + Alt + T.
2. Run TheHarvester:
TheHarvester is a command-line tool. To see the available options, you can run:

bash
Copy code
theharvester -h
3. Example Email Harvesting:
To perform email harvesting, you can use the following command:

bash
Copy code
theharvester -d example.com -l 500 -b google
Replace example.com with the target domain. This command uses the Google search engine (-b google) and limits the results to 500 (-l 500).

4. Example DNS Subdomain Enumeration:
To perform DNS subdomain enumeration, you can use the following command:

bash
Copy code
theharvester -d example.com -l 500 -b all
This command uses multiple sources (-b all) for subdomain enumeration.

5. Save Results to a File:
You can save the results to a file using the -f option. For example:

bash
Copy code
theharvester -d example.com -l 500 -b all -f results.html
This will save the results in HTML format to a file named results.html.

6. Explore Other Options:
TheHarvester supports various sources (-b option), and you can customize your searches based on your requirements.
7. Review Output:
After running TheHarvester, review the output to gather information about the target.
Note:
TheHarvester is a reconnaissance tool, and it's essential to use it responsibly and within legal and ethical boundaries. Always ensure that you have proper authorization before using it against any target.

This guide provides instructions for using TheHarvester on Kali Linux. Customize the commands based on your specific requirements, and ensure you comply with legal and ethical standards.






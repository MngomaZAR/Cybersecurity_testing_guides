Recon-ng on Kali Linux
1. Open a Terminal:
Open a terminal on your Kali Linux system. You can usually find the terminal in the applications menu or use the shortcut Ctrl + Alt + T.
2. Launch Recon-ng:
Recon-ng is pre-installed on Kali Linux. You can launch it by typing:

bash
Copy code
recon-ng
3. Explore Modules:
Recon-ng organizes its functionality into modules. You can list available modules using:

bash
Copy code
show modules
4. Select a Workspace:
Recon-ng uses workspaces to manage data. Create or select a workspace:

bash
Copy code
workspace add my_workspace
workspace use my_workspace
5. Set API Keys:
Some modules require API keys. Set them using:

bash
Copy code
keys add <name_of_the_key> <api_key>
6. Run Modules:
To run a module, use the use command followed by the module name. For example, to use the recon/domains-contacts/whois_pocs module:

bash
Copy code
use recon/domains-contacts/whois_pocs
7. Configure Module Options:
Before running the module, configure its options using the show options and set commands. For example:

bash
Copy code
set SOURCE example.com
8. Run the Module:
Execute the module using the run command:

bash
Copy code
run
9. Review Results:
After running a module, review the results using the show command. For example:

bash
Copy code
show hosts
10. Exit Recon-ng:
When you're done, exit Recon-ng:

bash
Copy code
exit
11. Optional: Save the Workspace:
If you want to save your workspace:

bash
Copy code
workspace save
12. Update Recon-ng:
Periodically update Recon-ng to get the latest modules:

bash
Copy code
recon-ng update
Note:
Recon-ng is a versatile framework with numerous modules. Explore the available modules and their options to customize your reconnaissance.
Always ensure that you have proper authorization before using Recon-ng on any network or system.
Refer to the Recon-ng documentation and help commands (help within the framework) for detailed information about modules and usage.
This guide provides basic instructions for using Recon-ng on Kali Linux.
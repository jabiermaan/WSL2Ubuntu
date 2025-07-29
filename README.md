# WSL2Ubuntu
  How to run and manage Ubuntu Linux using Windows Subsystem for Linux (WSL) directly on Windows 11

# How WSL Works (Briefly)
* WSL 2 (the default for Windows 11 and recommended): WSL 2 uses a lightweight utility virtual machine (VM) with a real Linux kernel. This provides full system call
  compatibility and significantly improved file system performance compared to WSL 1. Even though it's a VM, it's highly integrated with Windows, feeling much more seamless
  than a traditional VM.

* Interoperability: WSL is designed for seamless interaction. You can run Linux commands from Windows (e.g., PowerShell), and you can access Windows files from Linux and vice-
  versa.

* Isolated Filesystem: Each WSL distribution (like your Ubuntu) has its own isolated Linux file system. This is where you should primarily store your Linux-related projects and
  files for optimal performance.

# Key Commands to Manage Your WSL Distributions
  These commands are run from Windows Command Prompt (CMD) or PowerShell, not inside your Ubuntu terminal unless specified.

# 1. List Installed Distributions:
* wsl --list --verbose
* wsl -l -v  (shorthand)

# 2. Launch a Specific Distribution:
* wsl -d Ubuntu

# 3. Set a Default Distribution:
* wsl --set-default Ubuntu
* wsl -s Ubuntu (shorthand)

# 4. Terminate a Running Distribution:
* wsl --terminate Ubuntu
* wsl -t Ubuntu (shorthand)

# 5. Shut Down All WSL Instances:
* wsl --shutdown

# 6. Check WSL Version (1 or 2):
* wsl --set-version Ubuntu 2

# 7. Set Default WSL Version for New Installations:
* wsl --set-default-version 2
  
# 8. Update the WSL Kernel:
* wsl --update

# 9. Unregister (Delete) a Distribution: <ins>(WARNING: This permanently deletes the specified Linux distribution and ALL its data. This action is irreversible. Only use this if you want to completely remove a WSL distribution.) </ins>
* wsl --unregister Ubuntu
 
# Essential Linux Commands (inside your Ubuntu terminal)

# 10. Update Package Lists and Upgrade Software:
* sudo apt update => Refreshes the list of available packages and their versions. Do this often!
* sudo apt upgrade => Installs the newer versions of packages you have installed.

# 11. Install New Software:
* sudo apt install <package_name> => Example: sudo apt install git

# 12. Remove Software:
* sudo apt remove <package_name>
* sudo apt purge <package_name> (removes config files too)

# 13. Navigate Directories:
* pwd            # Print Working Directory (shows your current location)
* ls             # List files and directories
* ls -l          # Long format list (more details)
* ls -a          # List all files, including hidden ones
* cd <directory> # Change Directory
* cd ..          # Go up one directory
* cd ~           # Go to your home directory

# 14. File Operations:
* mkdir <directory_name>   # Make a new directory
* touch <file_name>        # Create an empty file
* cp <source> <destination> # Copy files or directories
* mv <source> <destination> # Move/Rename files or directories
* rm <file_name>           # Remove a file
* rm -r <directory_name>   # Remove a directory and its contents (use with caution!)
* cat <file_name>          # Display file contents
* nano <file_name>         # Open a simple text editor
* vim <file_name>          # Open the powerful Vim text editor (learning curve involved!)

# 15. User Management (within Ubuntu):
* whoami         # Show current user
* sudo adduser <new_username> # Add a new user
* sudo deluser <username>     # Delete a user
* sudo usermod -aG sudo <username> # Grant sudo (administrator) privileges to a user

# 16. Check Disk Usage:
* df -h          # Disk Free (human-readable)
* du -sh <directory> # Disk Usage (summarized, human-readable for a directory)

# 17. File System Integration (The "How It Works" Part): This is crucial for understanding how Windows and Ubuntu coexist:
  Accessing Windows Files from WSL:
  Your Windows drives are automatically mounted under /mnt/.
  Your C: drive is at /mnt/c
  Your D: drive (if you have one) is at /mnt/d
  You can navigate to these paths in your Ubuntu terminal:

* cd /mnt/c/Users/YourWindowsUsername/Documents

# Important: While you can access and modify Windows files from WSL, for performance and reliability reasons, it is strongly recommended to do your primary development and  store your Linux-related project files within the WSL filesystem itself (e.g., in your Ubuntu home directory, /home/yourusername/projects).

# 18. Accessing WSL Files from Windows:
You can access your Ubuntu file system directly from Windows File Explorer!

* Open File Explorer.
* In the address bar, type \\wsl$ and press Enter.
You will see a list of your installed WSL distributions (e.g., Ubuntu). Click on it to browse its Linux file system.
You can also open the current WSL directory in Windows File Explorer directly from the Ubuntu terminal:
* explorer.exe .  ** (The . means the current directory).**

# 19. Running Windows Executables from WSL:
* notepad.exe
* code . # Opens VS Code in the current WSL directory

# 20. Running Linux Commands from Windows:
* wsl ls -la
* wsl python3 my_script.py

# 21. Open Command Prompt as Administrator to Install WSL + Ubuntu Quickly
* wsl --install

# 21. Run the following command on CMD or Powershell to install Ubuntu on Windows:
* wsl --install -d Ubuntu
* wsl --list --verbose

# 1. How to check if Ubuntu is your default WSL distribution:
* wsl --list --verbose

# Look for an asterisk (*) next to one of the distribution names. The distribution with the asterisk is your default.

# 2. How to set Ubuntu as your default WSL distribution:
* wsl --set-default Ubuntu
The operation completed successfully.









# Ubuntu Desktop and Command Line Familiarisation  

## Ubuntu Desktop GUI Familiarisation  

1. I check the internet using the default browser - Firefox  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ec4bac51-8732-49eb-9925-9660ca50c922" />

2. I open LibreOffice and type a document  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/4470ecc7-cf8c-479b-a401-0a95b6dcb665" />

3. I navigate directories using File Manager  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/caa403e5-66dc-4298-90ca-8ee8bea05e44" />

4. I install a program via Ubuntu Software Centre  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/f019945f-b8ac-4be9-ab22-c30ecc387dc5" />

5. I visualize file changes by placing terminal and file browser side-by-side  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/37e96f0f-d776-425f-b9b2-c1e89e79b0c2" />  
   Description : I use the cd (change directory) command to enter the Documents file, ~/ is a built in shortcut for absolute path, and touch command is initially used to update the last modified timestamp of a file, However if the file you specify doesn't exist yet, touch will automatically screate a brand new, completely blank file with that name.  

## Ubuntu CLI Familiarisation  

1. Current Directory Printing by using the command 'pwd'  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/69ae7ad3-06b2-4911-a858-34566f7e0e16" />  

2. Processes monitoring by using the command 'ps  -e' , 'top' , and '1'  
   ps = Process Status, so by default typing ps will only shows the processes running in your terminal window.  
   -e = Adding -e tells the command to select every single process currently running on the entire os including the background system tasks.  
   Typing ps  -e together will how a long static list scroll past showing PIDs, the terminal they belong to (TTY), execution time and the command name. PIDs means Process ID, TTY means which terminal it runs on, TIME means the total CPU execution time, CMD means the name of the command.  
   top = a real, dynamic view for system’s activity. It continuous update every few seconds, displaying the overall CPU usage, memory consumption, uptime and sorting the hungriest processes right at the top of the list.  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/cdea0dda-fd1a-40c6-b219-f652443a6f09" />  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/3f16edc2-d37f-4955-8fd7-a5c4ef56f5d6" />

3. Explore files by using the command 'ls' , 'ls -la' , 'ls -alt' , 'ls -lah'

   ls = Standard list. This is the most basic form of the command. It simply prints a flat list of the names of visible files and folders in your current directory. It doesn’t give you any extra details like file size, permissions or creation dates.  
   <img width="300" height="100" alt="image" src="https://github.com/user-attachments/assets/e9e0e2cf-93bb-4b10-ada6-497f548e49ca" />

   ls -la = Long list + all files (this combine two flags : -a and -l). -a (All hidden file), This flag forces the terminal to reveal absolutely everything including the hidden file. -l (Long format), this flag converts the output from a simple list of names into a detailed, 7-column table. It also shows the file permissions, the owner of the file, the group it belongs to, the size in bytes, and the last modified timestamp.
   <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/e462e0ec-2c70-4beb-87ab-f5e667c55071" />

   ls -alt = Long list + all file + sorted by time. A new flag is added into the command, -t. this tells the system to sort the list by the most recent modified files first.  
   <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/598893f6-2680-4c96-b4ee-356027410270" />

   ls -lah = Long list + All files + Human readable. In a standard long list, file sizes are printed strictly in raw bytes. For example a 4 mega-byte file shows up as 4096. Adding -h will automatically convert those raw byte numbers into easy-to-read formats like 4.0M, 25K, or 2G
   <img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/14f584d4-ba10-4467-a24b-8e4cfc0ff703" />

4. Create/edit/view files using the command 'touch' , 'gedit' , 'nano' , 'cat' , 'less'.

   touch = this is designed to update the ‘last modified’ timestamp of an existing file. It is a most common shortcut for creating a empty file. If you run touch on a file name that does not exist yet, Linux will instantly creates a brand new, completely empty file with that name.
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/6d3c5861-56c2-4027-9dad-d80522fa2a6b" />

   nano = a lightweight, completely text-based editor that runs inside your terminal window. This is what systems engineers use when managing servers remotely where there is no graphical desktop environment available at all.
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/71f04f35-f7cf-4854-bbc2-71ad5c6ca64b" />

   gedit = a standard graphical text editor window (similar to Notepad on windows). It requires a GUI to run.
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/62e3809c-be0f-4247-a0cc-3e9ae6dbf9e3" />

   cat = Concatenate / quick print. It is most commonly used to quickly view the content of a short text file without opening an editor. It dumps the entire text file directly into your terminal output instantly.  

Example, I use gedit to save a copy of txt file containing the string ‘I am learning Linux Command Line’ and use cat to display the content over the terminal.  

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/fed97c69-cca4-4fe1-8734-d31a8dfbe4b5" />  

   less = if you use cat on a massive file with 10,000 lines, it will violently scroll past your screen, and you will only see the very bottom of it. less solves this by opening files in a scrollable view window. It help navigate long file page by page using your arrow keys without loading the entire massive file into the system memory all at once. (press q to quit)  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/03af5e43-9580-45e6-821d-0ba942a89c94" />  

5. Copy and move files with the command 'cp' , 'mv' and delete with the command 'rm' .  

    cp = this command duplicates an existing file from a source file from a source path to a destination path, leaving the original file completely untouched.    
The syntax : cp (source_file) (destination_file)  
    <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/8618a73d-c5ee-413a-8f02-5f1bcdd7ee00" />
   mv = this command is used to move files or rename file.   
   Syntax = move files: mv (source file) (destination path)   
   Syntax = rename files:  mv (source file) (new name file)   
   Syntax = both move files and rename files: mv (source file) (destination path/new name file)  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/4c59e6a5-65a7-4f87-b33f-068252a75da1" />  

   rm = Remove / delete. This command will deletes a file from the directory. Things to note, Linux doesn’t have a trash bin in the CLI. Once you hit enter on an rm command, the file is instantly and permanently destroyed. There is no undo.   
Syntax = rm (file name)  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/02ceb774-8dc1-4d31-b2f1-df680fe43dd9" />  

6. View System info using 'uname -a' , 'lsb release -a' , 'hostnamectl'  

   uname -a = uname prints information about the underlying system architecture and the os kernel. By default, typing just uname simply prints Linux. Adding the -a flag forces it to print all available system details in a single string.  
   
    uname  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c8e8de8c-f390-4589-9bff-8ed5fa42e29d" />  
    uname -a  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/9fa12d6f-ac66-4117-9572-2307a9c9078e" />  

   lsb_release -a = while uname tells about raw kernel, lsb_release tells you about the specific distribution layout built on top of that kernel (like Ubuntu, Debian or Red Hat). The -a flag prints a complete version of the distribution details.  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/6e6bfb45-1253-4ae5-bad3-52c1edf16985" />  

   Hostnamectl (Host name control) = this is used to query and change the system hostname and related settings. Running it without any arguments acts a comprehensive summary dashboard. It will display on computer’s network name, the icon name, the chassis type, the os name, the kernel string and the CPU architecture.  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/36fdb481-33a2-48dc-aedb-9bacaf6a2ae2" />

   ## Super User and Permission

   1. Demonstrating privilege escalation using the command 'whoami' , 'sudo whoami'  
  
      whoami = Identity check, this command queries the system to prints the exact username of the account currently controlling the terminal session  
      <img width="500" height="100" alt="image" src="https://github.com/user-attachments/assets/209dea49-1991-4c6b-bd94-2fa672bd294c" />  

      sudo whoami = sudo means Super User Do, it is a prefix command that tells Linux to temporary elevate the security privileges to execute the following command as the root administrative user. The system will prompt for the password, type it in and enter, the sudo successfully escalated the privileges, the termninal will print root instead of the username. This is the evidence of privilege escalation.  
      <img width="292" height="130" alt="image" src="https://github.com/user-attachments/assets/f5dc9917-b134-4dee-ac36-80b7e5e5b48a" />  

    2. Attemp add another user using the command 'adduser' as regular user and then with sudo  
  
       adduser without sudo = Linux will flat out reject the command, throwing a permission error like Permission denied or only Root may add a user to the system.  
       <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/840f109e-d54c-4faa-bf04-e63143959165" />  

       Whereas adduser with sudo = Because invoke the root user’s authority, the system will bypass the restriction, create the user configuration files and prompt you to set a new passwprd for the new user. Hit Ctrl + C or finish the prompt to exit once it works.  
       <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ce46eb33-d014-4d15-ba1a-64a17441210a" />   

       
## Role of Root User and Best practices for privilege use    

In the Linux world, the root user is the absolute master account, often referred to as the Superuser. It has unlimited power, unlike the administrative accounts in Windows that can still be blocked by system files, the root user has 0 restrictions. It can read, modify or delete any files on the entire system, shut down core hardware processes and alter network interface.  
Because root has no safety rails, a single typo can be catastrophic. For example, running a destructive command like rm -rf / as a normal user will fail with a permission error, but running as a root user will instantly wipe out your entire os. Deleting every single line from the root directory downward without asking ‘Are You Sure?’.  

So, The best practice  
1.	Never Log in directly as root user = in modern distribution like Ubuntu, the root account is actually locked by default, it doesn’t even have a usable password to log into. Instead, you log in as a regular user and use sudo to run specific administrative commands. This ensures you only hold dangerous prvileges for the split second it takes to execute that single command.  
2.	The principles of Least Privilege (PoLP) = This rules stated that a user, a program, or script should only have the exact minimum privilege necessary to complete its job and no more.  
3.	Audit trails and accountability = When multiple engineers manage an enterprise server, sharing a root pw makes it impossible to know who did what. Using sudo solves this because Linux logs every single sudo command to a system file (usually /var/log/auth.log). The log records exactly which username executed the command, what commaned they run and when they did it.  
4.	Think before you press enter = simple as that, think twice before you press enter, double check on your syntax.   





   

   




   






   
   
 

   



   







   



   






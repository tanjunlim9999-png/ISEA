# Linux Services, SSH, Firewalls & Compression  

## Apache2 Installation  

1. Install Apache2 by using the command 'sudo apt install apache2'

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/a4a3bb40-4771-48c0-a40a-bd6d2b707c9c" />

2. Testing the Domain using default Browser using IP address

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/7050b90c-6fa5-42dc-b010-7d6b2d023ee7" />

## SSH server & Nmap Installation  

1. Installing the SSH server and Nmap using the command : ‘sudo apt install openssh-server nmap’

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/21d3accd-33de-4a8d-a7f5-3afaaff17135" />
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/bbba8559-7065-486e-a2a0-5fc7a6529931" />

## Editing the HTML files  

We can actually edit the HTML files using the sudo and nano command  
1. Edit the html using the command ‘sudo nano /var/www/html/index.html

   <img width="502" height="45" alt="image" src="https://github.com/user-attachments/assets/9b01b861-a6a4-466b-b44a-796044c6e5e8" />

2. Use Nano terminal text editor to change the content of the webpage

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/e7403b3f-5b8b-4886-a3f6-bdb8ce787008" />

3. I changed the head and the title, testing with the default browser 'firefox'

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/26350de3-2876-40f2-bef6-3a2300561784" />


   ## The function of Nmap

   Nmap stands for Network Mapper. It is a powerful;, open source tool used by network administrator and security professionals for network discovery and security auditing.
Imagine Linux server is a massive apartment building with many doors (network ports basically). So when a service is running, example, Apache wed server, it unlocks a specific door (Port 80) and waits for visitors. Nmap acts as a security inspector. When we point Nmap at an IP address, it rapidly walks down the hallway and knocks on thousands of these doors. If a door is open and a service answers, Nmap report back to you, telling you exactly which doors are unlocked and what kind of service is living behind them.
Something I get to know from using AI tools for myself, Hackers can use Nmap to find vulnerable, open doors to break into. System administrators use Nmap to ensure that only doors they want to open are actually open.

1. The Before scan

   Scan against IP address 127.0.0.1  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/056dbfd4-4fc2-41ec-b691-d95acbb1237d" />  

2. Remove the Apache2 by using command 'sudo apt remove apache2 -y'  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/08e5e0c6-b04b-4088-b67b-5f4a390de699" />  

3. The After scan  

   Scan again using the command 'nmap' against 127.0.0.1  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/540e3fc6-1aaf-4225-b7d0-2425294d7826" />  

   Noticed that the port 80 (HTTP) has completely vanished from the list of open ports.  


## The use of UFW  

To check the firewall status, we can run the command 'sudo ufw status verbose'  

<img width="500" height="150" alt="image" src="https://github.com/user-attachments/assets/78026033-09b1-4037-b2bd-aae634ffa59d" />  

Looks like the firewall is currently inactive, in fact it always inactive by default  

Now, Allow the web traffic by using the command 'sudo ufw allow 80'  

<img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/53fc3fef-857e-4286-968d-1a672542f435" />  

Enable the firewall by using the command 'sudo ufw enable'  
<img width="444" height="172" alt="image" src="https://github.com/user-attachments/assets/8b3af080-6cb8-45a1-8ef9-464539246e1d" />  

The after check by using command 'sudo ufw status verbose' again  
<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/bcf16594-61b2-465d-af5c-053e24a5ce29" />  

The purpose of this actions is to establish network access control and secure the server from unauthorized traffic using UFW which stands for Uncomplicated Firewall.
By default, the firewall on a fresh Ubuntu installation is installed but inactive. 
Firstly, we check on the firewall status first to ensure its inactive.
Secondly, Because the firewall acts like a digital bouncer at the door of the server, so its default behavior is to deny all for incoming connection. That’s why we send command to allow for port 80 connection which is the HTTP to allow web traffic.
Thirdly, enable the firewall service to start actively monitoring and filtering network traffic based on the rules I just set.  

## Troubleshoot SSH connection issue using ufw rules  

We can use troubleshoot connection issue using the ufw rules  
For example SSH  

1. Check if the SSH connection is blocked.

   <img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/cf8389ef-ac12-430c-b93f-5dd029ee897b" />

2. Yes, it is blocked and encoutered issue, Ctrl + c to close
3. Allow the firewall to open door for port 22 (SSH) by using the command 'sudo ufw allow 22'

   <img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/2cfd2a8c-bcb1-4ed3-ae9c-2c7f82e3320a" />

4. Test again if SSH can be connected

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/476b5235-f4e7-4baa-9438-b5f56a838b1f" />

Yes, SSH is connected.  


## The use of mkdir, wget and compression commands  

We can create a directory by using command 'mkdir' and download 10 books into the directory using command 'wget'  

1. Create a directory named books by using the command ‘mkdir -p books’ and change directory to books

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ba22ed24-9c8e-47c6-98ca-db987da44a2c" />

2. Using the wget command to download 10 books from project Gutenberg

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/61efd686-05a8-447d-bb10-c1c41bea2642" />
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/5d544b7a-21d1-4c16-afbf-07a9b525f833" />

We can bundle the directory suing tar and compress the archive using bzip2 (if not yet install, can install it by using the command sudo apt install bzip2)  

<img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/ab107e9e-b1a3-40c2-8113-6f4915335187" />  


## Summary Questions  

To Summarize the whole lab activity 1b-1  

•	What’s the role of a firewall in managing services?  
A firewall acts as the ultimate gatekeeper for theserver. Instead of leaving every port open to the internet, a firewall allows administrators to dictate which specific services are allowed to communicate outwards or accept incoming traffic. This minimizes the server’s attack surface and keeps unauthorized users out.  

•	How did SSH access deepen your understanding of Linux as a server?  
SSH stands for Secure Shell, practically demonstrates that a Linux server is entirely self sufficient without a GUI. It shows that complete system administration, configuration, and maintenance can be executed remotely via a command line interface, which is exactly how enterprise data centers and cloud servers operate in the real world.  


•	Why is file compression important in server contexts?  
Servers constantly generate and process large amounts of datam such as system logs, database backups, and web assets. Compressing these files reduces their physical footprint on the hard drive. Smaller files require significantly less bandwidth and time to transfer across a network via tools like SCP.  


•	How does user privilege management help secure systems?  
User privilege management enforces the Polp (Principles of least privilege). By creating separate accounts and restricting access to root commands via sudo, you ensure that a user can only alter their own files. If a standard user’s account is compromised by a hacker, or if the user imply makes a careless mistake, the core operating system and other user’s data remain completely protected.  

 







   














   










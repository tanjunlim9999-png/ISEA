# Linux File Permissions and Group Access Control  


This Lab guide us through step by step on  
- How to create users and user groups in a Linux system
- Configure file and directory permission
- Understand the use of group ownership to manage access
- Apply and test file permissions for read, write and execute scenarios.
- Use commands such as su, whoami and ls -l to verify permissions

## Let setup and Instructions  

1. Create users for alice, bob and mallory using the command 'sudo adduser alice', 'sudo adduser bob', 'sudo adduser mallory'.

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/c551c666-df84-4a1a-a7ba-c2c288364dd1" />

2. Create a Group by using command 'sudo groupadd sharedgroup', create a directory by using the command 'sudo mkdir /home/shared', and create ten files inside it by using the command 'sudo touch /home/shared/file{1..10}'

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/a647852d-84fa-418c-8694-54fe8d1be46d" />

3. Change group ownership by using the command 'sudo chgrp -R sharedgroup /home/shared'

   <img width="500" height="50" alt="image" src="https://github.com/user-attachments/assets/d10fe582-2721-44fe-8fae-c9b203ff4d3d" />

4. Check on the file creation by using the command sudo ;ls -l /home/shared

   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/29cbd6fd-bfad-4981-a801-0e261576168f" />

5. Add alice and bob to group by using the command 'sudo usermod -aG sharedgroup alice' and 'sudo usermod -aG sharedgroup bob'

   <img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/e1dcbc06-075d-4510-b53f-83dcc52519cf" />

6. Set directory permissions: 'sudo chmod -R 770 /home/shared'

   <img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/4ceb5a3e-6bdb-4220-8a07-471c12947b3d" />

7. Override all file permission to 'sudo chmod 750 /home/shared/*'

   <img width="500" height="110" alt="image" src="https://github.com/user-attachments/assets/f4bc0001-c9ca-4ff9-998b-c98c25262526" />

   However Noticed that there’s an error prompt because the terminal tries to figure out what is the * means before the sudo command actually activates. My normal user account doesn’t have the permission to look inside the folder anymore because we locked it down to 770 in the previous step, so the terminal gets blocked, gives up and searches for a file named *.  

To fix this issue, we just wrap the command in quotes so the whole thing (Including the *) is handed over to the superuser to execute.  
I change the command to ‘sudo bash -c “chmod 750 /home/shared/*”.  

So this command will remove the write access on all the files in the destination folder.  

Lets check the permission using the command sudo ls -l /home/shared  


<img width="500" height="250" alt="image" src="https://github.com/user-attachments/assets/8882b9f7-76fb-4106-b56c-248045344c87" />  

8. Remove mallory from any group with access

   We can remove Mallory access from the group by using the command ‘deluser’
So the full command is ‘sudo deluser mallory sharedgroup’

<img width="500" height="100" alt="image" src="https://github.com/user-attachments/assets/38833f75-8967-4388-8f45-cf5ea69b3ec1" />  

9. Switch between user using the su command, whoami and ls -l /home/shared to verify access  
 
    For alice user account  
   <img width="500" height="300" alt="image" src="https://github.com/user-attachments/assets/a7e92a9a-bba4-425c-be5c-d5f72d3d8870" />

   For bob user account is the same as alice, Lets move on to mallory user account

   For mallory user account, permission denied as we have removed the access from shared group

   <img width="500" height="100" alt="image" src="https://github.com/user-attachments/assets/32fb7e66-428d-49eb-972f-7301f81e1095" />


   ## Relection questions  

- How do Linux permissions differ from Windows ACL?

   Linux uses a strict, streamlined 3x3 model. You can only assign permissions (Read, Write, Execute) to exactly three entities per file: the single Owner, a single Group, and      Everyone Else (Others). Whereas Windows uses a highly granular, list-based system. You can explicitly allow or deny specific permissions to dozens of different individual users  and multiple groups at the same time on a single file, and it features complex rules for how folders pass those permissions down to files (inheritance).  

  

- What’s the effect of chmod 770 vs 750?  
 chmod 770 grants the Owner and the Group absolute full access—Read, Write, and Execute (rwx). Both the owner and group members can view, modify, and run the file. Others get zero access. chmod 750 grants the Owner full access (rwx), but restricts the Group to only Read and Execute (r-x). Group members can view or run the file, but their ability to edit, modify, or save over it is entirely removed. Others still get zero access.  


- What is the risk of adding users to the sudo group?  
Adding a user to the sudo group essentially hands them the master keys to the server. It allows them to temporarily elevate their account to the root superuser level. With sudo privileges, a user can bypass all security restrictions, read any private file on the system, alter core operating system configurations, change other users' passwords, or accidentally delete critical system files that break the entire machine.  

- Why is it important to verify with `su` and `whoami`?  
su (Substitute User) allows you to physically step into that user's shoes and interact with the environment exactly as they would, proving that the security restrictions actually work in practice. whoami is extremely easy to lose track of which account you are actively using when bouncing between multiple profiles in a single terminal. Running whoami is a critical safety check to confirm your identity before you run a test, ensuring your screenshots and findings are perfectly accurate.  





   









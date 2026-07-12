# **Virtualisation & Linux Setup**

## Installation of Virtual Box and Ubuntu Linux Environment

Step 1. Go to https://www.virtualbox.org/ to download and install the Oracle VirtualBox



<img width="2846" height="934" alt="image" src="https://github.com/user-attachments/assets/64965a89-d331-4da5-973f-e72f25a9443a" />



Step 2. Go to https://ubuntu.com/download/desktop to download latest Ubuntu Desktop



<img width="2848" height="1404" alt="image" src="https://github.com/user-attachments/assets/87bfaab4-3421-4263-95a8-b34847fd7e5a" />



Step 3. Open the Oracle Virtualbox manager and click on <img width="30" height="50" alt="image" src="https://github.com/user-attachments/assets/45a36d91-9747-4f26-bb23-ada69a4a9891" /> create a new Virtual Machine

Step 4. Name the VM accordingly and choose the downloaded Ubuntu ISO file as ISO image



<img width="1598" height="1096" alt="image" src="https://github.com/user-attachments/assets/7b2de89a-6141-4f7c-8f36-6cfa33ad60bf" />



Step 5. Specify the virtual hardware, Make sure to allocate wisely to avoid starving the host operating system



<img width="1272" height="296" alt="image" src="https://github.com/user-attachments/assets/9a3eb325-cab6-4fb2-8119-a460d08be620" />



Step 6. Click finish and start the installation, the installation will take a few minutes to complete 

Step 7. After the installation, the virtual machine will reboot and start with the setting up and registration of the user account in Ubuntu Deskstop.  

Step 8. After setting up the account, Ubuntu desktop is ready to use  



<img width="1916" height="1234" alt="image" src="https://github.com/user-attachments/assets/e5e1043b-0cfa-47f9-8329-3d90e83cd470" />  



# Challenges during the installation

1. Installation Freezes and Repeated Restarts  
During the OS installation phase (specifically during the file extraction and update process), the virtual machine GUI froze completely. The progress bar stopped moving, and the system became unresponsive, forcing me to restart the virtual machine several times.  
Solution : I performed a forced ACPI shutdown from the VirtualBox machine menu. Upon restarting, I realized the freeze was likely caused by resource exhaustion. Ensuring no heavy applications were running on my host machine allowed the local installation to finish smoothly.






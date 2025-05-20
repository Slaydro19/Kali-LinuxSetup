# Kali-LinuxSetup
Installing Kali Linux to windows (WSL2) 

## Getting this error after installing Kali from the Microsoft Store?

```
WslRegisterDistribution failed with error: 0x80004005
```

If this happens to you, it means Kali didn’t register properly. Here’s how I fixed it:

1. Open PowerShell as Administrator
2. Run:
   ```
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   ```
3. Restart your computer
4. Open PowerShell (Admin) again and run:
   ```
   wsl --update
   ```
5. Then set WSL 2 as your default version:
   ```
   wsl --set-default-version 2
   ```
6. Finally, install Kali Linux directly through PowerShell:
   ```
   wsl --install -d kali-linux
   ```

After these steps, Kali launched correctly and asked me to set a username and password.


How i installed Kali Linux on a windows 11 machine 
 # What I used  -Windows 10/11
    
    -Windows Subsystem for Linux (WSL2)
     
      -Kali Linux | Downloaded from microsoft store
      
        -Powershell
# Make Sure you are running the latest version of Microsoft 
![Screenshot 2025-05-19 104230](https://github.com/user-attachments/assets/1bf798e3-40ea-4bff-9a74-6ae0de3ffbb5)
If you're unsure of which version of Windows you are running, simply type "winver" in the search bar and press enter

![Screenshot 2025-05-19 104613](https://github.com/user-attachments/assets/9b23a23c-48d5-41ee-83ca-fd607c3a6437)

If you dont have the prerequiste the website asks for just search "Update" in your search bar and install all current updates

![image](https://github.com/user-attachments/assets/99b46afd-8de6-498d-a7d9-f18624602112)

# Downloading and Installing Kali Linux  
1. Open the search bar again on your desktop and then type PowerShell. Make sure you run it as an administrator. You can either right click and hit "Run As Administrator"or, depending on which version of Windows you have installed, you won't need to click it right as it's already an option from the right side panel when you search using the search bar
2. When PowerShell is open, simply type or copy Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux. Once typed out or copied, simply hit enter, and this should appear

![Screenshot 2025-05-19 163705](https://github.com/user-attachments/assets/1fdfc0bd-816f-48d3-af0c-644ab5659591)


3. Wait for it to finish, and it's going to show another pop-up asking if you want to restart Simply hit "Y" and it will restart
4. Next, we will update the kernel package for WLS. Open a web browser and either type or copy https://aka.ms/wsl2kernel It will redirect you to a page where you're going to click underneath "Download the latest package"

![Screenshot 2025-05-19 162623](https://github.com/user-attachments/assets/a862cc71-cc80-466e-96a8-5b3d0d2d483f)

5. Now, when prompted, go through the installation wizard and once completed, reopen PowerShell and run it in administrator mode again
6. we are going to be setting WSL 2 as our default version and to do this simply copy and paste this command or type it in wsl --set-default-version 2. Once completed you should see this screen letting you know you have successfully completed this command. Also dont close PowerShell quite yet we still need it.

   ![Screenshot 2025-05-19 163918](https://github.com/user-attachments/assets/f8768646-4f55-4c1a-9ff4-bfa90ee98e94)

   7. Now the fun part, simply head over to the Microsoft Store, you can reach that by typing in the desktop search bar "Store" and it will appear. Once in the store, find the store's search bar and type "Kali Linux" Click on the page and download it. Once finished, close the store App and proceed to the desktop search bar, once there, search and find "Kali Linux", once found, open it

      *DISCLAIMER* make sure you wait on the store page, closing it early can cause it to not download and will have to reopen to properly have it installed.

 ![Screenshot 2025-05-19 164222](https://github.com/user-attachments/assets/af02e22c-cb48-4cd9-9f18-88d9c94935da)

8. Once opened, it will prompt you to create a username and password so fill it out to whatever you'll remember


## What I Learned

- Installing Kali from the Microsoft Store won’t work unless WSL 2 is fully set up first
- PowerShell must be run as Administrator or commands silently fail
- That `0x80004005` error is common and fixable, but most tutorials skip it

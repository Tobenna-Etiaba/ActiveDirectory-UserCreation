<p align="center">
<img src="https://i.imgur.com/aMMGyHQ.jpeg" height="80%" width="80%" alt="Setting Up in Azure"/>
<br />

<h1>ActiveDirectory (Part 2 - Joining The VMs & Creating Users)</h1>
Following up on the setup I will be demonstrating how I was able to join the Windows 10 VM to the Windows server as well as creating a wide array of users that can log into the Windows 10 VM.

<h2>Tools Used</h2>

- Microsoft Azure
- Remote Desktop
- Powershell

<h2>Operating Systems Used</h2>

- Windows 10
- Windows Server 2022

<h2>Step By Step Process</h2>

- From within the Windows Server VM*(will be calling it Server from here on out)* I went to the server manager to install active directory domain services.

<img width="637" alt="Screenshot 2025-02-07 at 13 17 30" src="https://github.com/user-attachments/assets/5d70559a-88b7-4ef2-b62c-ff5dd28293ac" />

<img width="784" alt="Screenshot 2025-02-07 at 13 18 15" src="https://github.com/user-attachments/assets/1037f974-fbc2-46b1-b0ce-28b4e84c78b1" />

<img width="787" alt="Screenshot 2025-02-07 at 13 22 10" src="https://github.com/user-attachments/assets/2b38529e-2307-4d54-9520-7d7c89dd8a00" />

- The next thing to do was to promote Server as a domain controller and set up a new forest(I named it mydomain.com)

<img width="690" alt="Screenshot 2025-02-07 at 13 22 43" src="https://github.com/user-attachments/assets/3768ee42-70f5-4861-948b-386f7b76824f" />

<img width="761" alt="Screenshot 2025-02-07 at 13 23 39" src="https://github.com/user-attachments/assets/af0a6010-3ba2-4955-8dda-f15e62615709" />

<img width="761" alt="Screenshot 2025-02-07 at 13 24 08" src="https://github.com/user-attachments/assets/dc6f07ea-66ff-4ab8-9895-a949cf2696b3" />

<img width="760" alt="Screenshot 2025-02-07 at 13 27 16" src="https://github.com/user-attachments/assets/9e3f4481-9892-4d16-a91a-290c35042368" />

- I restarted Server from within Azure and then proceeded to log back in via a domain context. 

<img width="1666" alt="Screenshot 2025-02-07 at 13 29 19" src="https://github.com/user-attachments/assets/4adb2760-24b3-40f2-b828-8df8a54894bd" />

<img width="811" alt="Screenshot 2025-02-07 at 13 30 10" src="https://github.com/user-attachments/assets/2afcaabd-5a9e-4a80-8d98-47713e73ed40" />

<img width="1150" alt="Screenshot 2025-02-07 at 13 33 56" src="https://github.com/user-attachments/assets/06cc51d5-c329-4746-8c67-88b056ef79f1" />

- After logging back in I went to active directory users and computers and created 2 organisational units (I named them EMPLOYEES & ADMINS). From within ADMINS, I created a new user called Tony Stark(I assigned him the same password I have been using to login into the 2 VMs)

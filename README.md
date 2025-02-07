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

- After logging back in I went to active directory users and computers and created 2 organisational units (I named them EMPLOYEES & ADMINS). From within ADMINS, I created a new user called Tony Stark(I assigned him the same password I have been using to log into the 2 VMs, and I gave him the username tony_admin)

<img width="643" alt="Screenshot 2025-02-07 at 13 38 46" src="https://github.com/user-attachments/assets/c0ec5aa6-5645-4464-828b-840303544124" />

<img width="842" alt="Screenshot 2025-02-07 at 13 41 11" src="https://github.com/user-attachments/assets/526a5020-d223-47b0-8803-aa1184b5ba80" />

<img width="752" alt="Screenshot 2025-02-07 at 13 41 21" src="https://github.com/user-attachments/assets/486f265b-7698-4b71-9504-7c3aa1de8e3a" />

<img width="754" alt="Screenshot 2025-02-07 at 13 41 47" src="https://github.com/user-attachments/assets/ed07f86c-147d-4970-91ff-506127a86d74" />

<img width="437" alt="Screenshot 2025-02-07 at 13 42 11" src="https://github.com/user-attachments/assets/74802edf-daa1-474f-8642-dcc7f34b1c58" />

<img width="755" alt="Screenshot 2025-02-07 at 13 42 29" src="https://github.com/user-attachments/assets/77423d55-f633-4611-a3cc-636eb6415bcf" />

- I added Tony to the "Domain Admins Security group", then logged out and logged back in as tony_admin.

<img width="751" alt="Screenshot 2025-02-07 at 13 47 01" src="https://github.com/user-attachments/assets/c76be5c5-4801-42d6-9142-4b976cb2f835" />

<img width="907" alt="Screenshot 2025-02-07 at 13 47 41" src="https://github.com/user-attachments/assets/97882566-e8ef-4613-8347-f3b1db9501f0" />

<img width="1150" alt="Screenshot 2025-02-07 at 13 50 22" src="https://github.com/user-attachments/assets/ec63cf78-00f1-46d9-943f-d53f47cd9ab6" />

- After logging back in the next thing was to join the windows 10 VM (I'll be calling it User from here on out) to Server.

<img width="1178" alt="Screenshot 2025-02-07 at 13 52 44" src="https://github.com/user-attachments/assets/eeed621b-12c3-4966-8bee-507461bd76c5" />

<img width="411" alt="Screenshot 2025-02-07 at 13 53 28" src="https://github.com/user-attachments/assets/0f2c836b-a65a-4cf4-b994-f2b957a9b495" />

<img width="411" alt="Screenshot 2025-02-07 at 13 53 55" src="https://github.com/user-attachments/assets/19233798-15e4-4049-91a5-e70a2384fc16" />

<img width="457" alt="Screenshot 2025-02-07 at 13 56 32" src="https://github.com/user-attachments/assets/e1f77e1c-8d39-486e-8df6-6becf4f16d6a" />

- I logged back into to Server to confirm that User had shown up in active directory users and computers. I then created a new organisational unit called Clients and dragged User into it.

<img width="754" alt="Screenshot 2025-02-07 at 13 57 56" src="https://github.com/user-attachments/assets/80a10794-4f92-4e89-81da-0d0250df1464" />

<img width="747" alt="Screenshot 2025-02-07 at 13 59 34" src="https://github.com/user-attachments/assets/db4c4541-7153-4852-ae5f-1cd7b02d4511" />

<img width="754" alt="Screenshot 2025-02-07 at 13 59 52" src="https://github.com/user-attachments/assets/f0881190-ddb7-48de-b02e-860ec72d2ef5" />

- I logged back into User as *mydomain.com\tony_admin* and went to remote desktop to allow Domain Users access to remote desktop.

<img width="1200" alt="Screenshot 2025-02-07 at 14 02 28" src="https://github.com/user-attachments/assets/dd7bac09-6d9d-4385-970c-ca7586fbdccf" />

<img width="1201" alt="Screenshot 2025-02-07 at 14 02 41" src="https://github.com/user-attachments/assets/69b41182-6ffb-4e11-82f2-854bf59bb818" />

<img width="832" alt="Screenshot 2025-02-07 at 14 04 24" src="https://github.com/user-attachments/assets/4b20e997-ac5f-4398-b968-28625bb1a2f4" />

I logged back into Server and opened powershell ISE as an administrator and copied a pre-written script into and ran the code to create a whole bunch of users(The users created can be seen under _EMPLOYEES in active directory users and computers).

<img width="786" alt="Screenshot 2025-02-07 at 14 05 27" src="https://github.com/user-attachments/assets/08d5d001-3638-46db-9a75-3c54e1fb2fea" />

<img width="1376" alt="Screenshot 2025-02-07 at 14 07 59" src="https://github.com/user-attachments/assets/62c48a51-8110-4554-acb7-57c96384c467" />

<img width="1539" alt="Screenshot 2025-02-07 at 14 08 34" src="https://github.com/user-attachments/assets/a310efe5-49b9-40dc-ae64-cef2e776fba1" />

<img width="1133" alt="Screenshot 2025-02-07 at 14 08 59" src="https://github.com/user-attachments/assets/58a58698-7ef6-430e-a29a-6ad6da10fe40" />

<img width="753" alt="Screenshot 2025-02-07 at 14 09 53" src="https://github.com/user-attachments/assets/2cdb52ac-1117-43c2-bfdc-25a429b5c513" />

- I logged back into User using one of the created users from the script.

<img width="1146" alt="Screenshot 2025-02-07 at 14 18 04" src="https://github.com/user-attachments/assets/3131ea0c-84f5-4176-95ce-69b5420f4b97" />

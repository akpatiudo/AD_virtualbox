IT Support Technician – Network Setup Lab: An Interview Task For HelpDesk support 
📌 Scenario:
You are an IT Support Technician at KevTech Academy, and your Network Administrator has given you a set of tasks to complete. Follow the steps carefully to set up the network correctly.
You are an IT Support Technician at kevtech Academy and the  Network Administrator has tasked you with making the  following changes to the network:  
1. Use the table below creating the following staff user  accounts, their respective departments are also  shown  2. Create a network drive called "kevtech shared files"  that is accessible to all users. Within it, create a  folder for each department that can only be  accessed by the members of each write to their  departments folder. Save a file and name it with the  chosen user name (user Snipping tool save evidence  of this on the Vm Host)  3. Rename Server to "SVR-01" a domain controller for  the domain controller kevtech.com  
Sales  |HR  finance  Bob Smith | Billy Banes | Holly Cross

🔹 Task 1: Create User Accounts in Active Directory
👉 You need to create user accounts for employees and assign them to their correct departments.

✅ Instructions:

Open Active Directory Users and Computers (ADUC)
Press Win + R, type dsa.msc, and press Enter.
Create an Organizational Unit (OU) for Staff
Right-click on kevtech.com → New → Organizational Unit.
Name it Staff.
Add the Following Users to AD:
Department	User Full Name	Username
Sales	Bob Smith	bsmith
HR	Billy Banes	bbanes
Finance	Holly Cross	hcross
Set a default password and enable "User must change password at next login".
📸 Proof: Take a screenshot of the users in ADUC.

🔹 Task 2: Create a Shared Network Drive
👉 You need to set up a network drive where employees can store files.

✅ Instructions:

Create a Shared Folder
Open File Explorer → Go to C:\ → Create a folder called Kevtech Shared Files.
Create Department Folders Inside It:
Sales, HR, Finance
Set Folder Permissions:
Right-click each folder → Properties → Security → Advanced.
Give Modify access to each department's users only.
Share the Folder:
Right-click Kevtech Shared Files → Properties → Sharing → Advanced Sharing.
Check "Share this folder" and allow Read access for Everyone.
Map the Network Drive for Users
Open Group Policy Management (gpmc.msc)
Go to User Configuration → Preferences → Drive Maps
Map \\SVR-01\Kevtech Shared Files as a network drive.
📸 Proof: Save a test file in one of the department folders and take a screenshot.

🔹 Task 3: Rename the Server and Set Up a Domain Controller
👉 You need to rename the server and make it the main controller for the kevtech.com domain.

✅ Instructions:

Rename the Server
Right-click Start → System → Rename this PC.
Change the name to SVR-01.
Restart the server.
Promote Server to Domain Controller
Open Server Manager → Add Roles and Features.
Install Active Directory Domain Services (AD DS).
Click "Promote this server to a domain controller".
Set domain name to kevtech.com and complete the setup.
Restart the server when prompted.
📸 Proof: Take a screenshot of the Server Name and Domain Controller Status.

🔹 Task 4: Test User Access to Shared Folders
👉 Now, check if users can access the correct folders.

✅ Instructions:

Log in as Bob Smith (Sales)
Open File Explorer → Go to Network → Open \\SVR-01\Kevtech Shared Files\Sales
Try to create and edit a file.
Try opening HR or Finance folders (you should be denied access).
Repeat for Billy Banes (HR) and Holly Cross (Finance).
📸 Proof: Take a screenshot showing access granted/denied.

🔹 Task 5: Save Evidence and Submit
👉 Once you have completed all the tasks, save all screenshots in a folder and submit your report.

✅ Instructions:

Create a folder named KevTech Setup Evidence on the desktop.
Save all screenshots inside the folder.
Submit it to your instructor or supervisor.
🎯 You Did It! 🎉
✅ You created users.
✅ You set up a shared drive with correct permissions.
✅ You configured a domain controller.
✅ You tested everything successfully!

💡 Want to test more? Try creating another user and assigning them permissions! 🚀

## part 2
IT Support Technician – Network Setup Lab: An Interview Task for HelpDesk Support
📌 Scenario:
You are applying for a HelpDesk Support role at KevTech Academy, and as part of your interview, the Network Administrator has assigned you a practical task. This task will test your ability to manage user accounts, shared network resources, and troubleshoot common issues.

⚡ Your goal: Complete the following tasks efficiently while documenting your steps and solutions.

🔹 Task 1: Create User Accounts in Active Directory
👉 Objective: Set up user accounts for employees and ensure they are assigned to the correct department.

✅ Instructions:

Access Active Directory Users and Computers (ADUC)
Press Win + R, type dsa.msc, and press Enter.
Create an Organizational Unit (OU) for Staff
Right-click on kevtech.com → New → Organizational Unit.
Name it Staff.
Add the Following Users to AD:
Department	User Full Name	Username
Sales	Bob Smith	bsmith
HR	Billy Banes	bbanes
Finance	Holly Cross	hcross
Set a default password and enable "User must change password at next login".
📸 Proof Required: Take a screenshot of the users in ADUC.

🚀 Bonus Question (Troubleshooting):

A user reports they can’t log in after you create their account. What steps would you take to resolve this?
🔹 Task 2: Create a Shared Network Drive and Set Permissions
👉 Objective: Create a shared folder structure for departments and restrict access based on their roles.

✅ Instructions:

Create a Shared Folder
Open File Explorer → Go to C:\ → Create a folder called Kevtech Shared Files.
Create Department-Specific Folders Inside It:
Sales, HR, Finance
Set Folder Permissions:
Right-click each folder → Properties → Security → Advanced.
Remove Everyone and only allow each department’s users Modify access to their own folders.
Share the Main Folder:
Right-click Kevtech Shared Files → Properties → Sharing → Advanced Sharing.
Check "Share this folder" and allow Read access for Everyone.
Map the Network Drive for Users
Open Group Policy Management (gpmc.msc)
Go to User Configuration → Preferences → Drive Maps
Map \\SVR-01\Kevtech Shared Files as a network drive.
📸 Proof Required: Save a test file inside the HR folder as HR_Test.txt, and take a screenshot.

🚀 Bonus Question (Troubleshooting):

A user in HR says they can’t access their HR folder but can see the shared drive. What would you check?
🔹 Task 3: Rename the Server and Set Up a Domain Controller
👉 Objective: Rename the server and configure it as a domain controller for kevtech.com.

✅ Instructions:

Rename the Server
Right-click Start → System → Rename this PC.
Change the name to SVR-01.
Restart the server.
Promote the Server to a Domain Controller
Open Server Manager → Add Roles and Features.
Install Active Directory Domain Services (AD DS).
Click "Promote this server to a domain controller".
Set domain name to kevtech.com and complete the setup.
Restart the server when prompted.
📸 Proof Required: Take a screenshot showing the Server Name and Domain Controller Status in Server Manager.

🚀 Bonus Question (Troubleshooting):

After renaming the server and promoting it to a domain controller, users can’t log in to the domain. What steps would you take to fix this?
🔹 Task 4: Test and Troubleshoot User Access to Shared Folders
👉 Objective: Verify that department users can access their assigned folders and cannot access others.

✅ Instructions:

Log in as Bob Smith (Sales)
Try opening \\SVR-01\Kevtech Shared Files\Sales (✅ Should work).
Try opening HR or Finance folders (❌ Should be denied).
Try creating a new file inside Sales.
Repeat for Billy Banes (HR) and Holly Cross (Finance).
📸 Proof Required: Take a screenshot of an access denied message for an unauthorized folder.

🚀 Bonus Question (Troubleshooting):

A Sales user reports they can’t save files in their department folder, but they can open it. How would you fix this?
🔹 Task 5: Save Evidence and Submit Your Work
👉 Objective: Ensure proper documentation and reporting.

✅ Instructions:

Create a folder named "KevTech Setup Evidence" on the desktop.
Save all screenshots inside this folder.
Write a short report (2-3 sentences) describing the steps you took and any troubleshooting issues you faced.
Submit your work to the interviewer/supervisor.
🎯 Final Check: Have You Completed Everything?
✅ Created user accounts & assigned them to departments
✅ Configured a shared drive with proper access control
✅ Renamed the server & promoted it to a domain controller
✅ Verified user access and fixed any issues
✅ Saved evidence and documented your work

💡 Interview Reflection:
If this were a real interview, the hiring manager might ask:

How would you handle a user forgetting their password?
What tools would you use to remotely assist a user?
How would you approach troubleshooting printer or network issues?
🚀 Pro Tip: Be ready to explain your thought process clearly, just like you did in this lab!

You Did It! 🎉
You've successfully completed a real-world HelpDesk Support task!
Would you like additional practice scenarios or need help with any step?

### troble shooting ans

🔹 Issue 1: User Can’t Log In After Account Creation
📌 Problem: A new user reports they can’t log in after you created their account in Active Directory.

✅ Troubleshooting Steps:

Verify the Account Exists:

Open Active Directory Users and Computers (ADUC) → Search for the user.
Ensure the account was created in the correct Organizational Unit (OU).
Check If the Account is Enabled:

Right-click the user account → Properties → Account Tab.
Ensure "Account is disabled" is NOT checked.
Confirm Username and Password:

Ensure the user is entering the correct username format (domain\username or username@domain.com).
Reset the password (Right-click → Reset Password) and select “User must change password at next login”.
Check if the User is Locked Out:

In ADUC, go to Properties → Account and check for "Account is locked out."
If locked out, uncheck the box and apply changes.
Ensure the Computer is Connected to the Domain:

Run ping domain.com in Command Prompt on the user’s PC.
If there’s no response, check the network settings and domain connectivity.
Try rejoining the computer to the domain (System Properties → Change → Domain).
Check Group Policy and Logon Restrictions:

Ensure the user is part of the correct security groups (e.g., “Domain Users”).
Check logon restrictions under Properties → Account → Logon Hours to ensure they are not blocked.
🔹 Issue 2: User Can’t Access HR Folder in the Shared Drive
📌 Problem: A user in HR can see the shared drive but cannot access the HR folder.

✅ Troubleshooting Steps:

Check Folder Permissions:

Right-click the HR folder → Properties → Security Tab.
Ensure the HR security group has Read/Write access.
If necessary, add the user manually (Add → Enter username → Assign Read/Write permissions).
Verify NTFS vs. Share Permissions:

Right-click HR folder → Properties → Sharing Tab → Advanced Sharing.
Ensure that "Everyone" has at least Read access.
Check NTFS permissions under the Security tab (should match share permissions).
Confirm Group Membership:

Open ADUC → Find the user → Properties → Member Of.
Ensure the user is in the HR Group.
If they are not, add them, then ask them to log out and back in.
Map the Network Drive Correctly:

Ensure the drive is mapped as \\ServerName\Kevtech Shared Files\HR.
Run net use in Command Prompt to check active mapped drives.
Check if the User’s PC is on the Same Network:

Run ipconfig /all and check if the IP address is in the same subnet as the server.
Run ping servername to ensure the PC can reach the shared folder.
Check Group Policy (GPO) for Drive Mapping Issues:

Run gpupdate /force to refresh Group Policies.
Check Group Policy Management (gpmc.msc) for incorrect drive mapping policies.
🔹 Issue 3: Users Can’t Log In After Renaming and Promoting Server to Domain Controller
📌 Problem: After renaming the server and promoting it to a Domain Controller, users are unable to log in.

✅ Troubleshooting Steps:

Check DNS Configuration:

Run ipconfig /all on client PCs and ensure their Primary DNS points to the new Domain Controller (DC).
On the DC, ensure DNS is running:
Open DNS Manager (dnsmgmt.msc) → Check if the domain zone exists.
If missing, recreate the Forward Lookup Zone for kevtech.com.
Ensure the Server Name Change Was Updated in AD:

Open Active Directory Users and Computers (ADUC).
Verify that the new DC name (SVR-01) appears under Domain Controllers.
Check Group Policy & Domain Trust:

Run gpupdate /force on the DC and client computers.
If users see "Trust relationship failed", rejoin the affected computers to the domain:
Open System Properties (sysdm.cpl).
Click Change → Workgroup → Apply → Restart.
Rejoin the kevtech.com domain and restart again.
Ensure Active Directory Services Are Running:

Run services.msc and check that the following are Running:
Active Directory Domain Services
Netlogon
DNS Server
Kerberos Key Distribution Center (KDC)
Check Event Viewer for Errors:

Open Event Viewer (eventvwr.msc) → Go to Windows Logs → System.
Look for errors related to Netlogon, Kerberos, or Group Policy.
Verify User Authentication via the Domain Controller:

Run echo %logonserver% on the user’s computer to confirm they are authenticating against the correct Domain Controller (SVR-01).
If not, restart the DC and run nltest /sc_verify:kevtech.com to test authentication.
🚀 Final Fix: If users still can’t log in, consider demoting and re-promoting the DC using dcpromo.exe.

🎯 Key Takeaways:
✔ Always verify user account status when troubleshooting login issues.
✔ Shared folder access issues are often due to misconfigured permissions or missing group memberships.
✔ After renaming a Domain Controller, ensure DNS and Group Policy are updated to prevent authentication issues.

Would you like me to create a step-by-step lab guide for practicing these troubleshooting scenarios? 😊



### part 3
IT Support Technician – Additional Interview Scenario & Troubleshooting Guide
📌 Scenario 2: IT HelpDesk Ticket – New Employee Setup & System Issues
A new employee, Jane Doe, has just joined the Marketing Department at KevTech Academy. Your manager has assigned you the following tasks to ensure she is ready to start work.

🔹 Task 1: Create Jane Doe’s User Account and Assign Proper Access
👉 Objective: Ensure Jane can log in and access her department’s shared files.

✅ Instructions:

Create Jane’s account in Active Directory (ADUC)

Open Active Directory Users and Computers (dsa.msc)
Navigate to kevtech.com → Staff
Right-click Staff → New → User
Fill in the following details:
Full Name: Jane Doe
Username: jdoe
Password: KevTech123! (User must change at next logon)
Click Next → Finish.
Assign Jane to the "Marketing" Group

Right-click Jane's account → Properties → Member Of
Click Add, type Marketing, and click OK.
📸 Proof Required: Screenshot of Jane’s account in ADUC.

🚀 Troubleshooting Issue #1: Jane Can’t Log In
🔎 Possible Causes & Fixes:
✅ Check if the account is enabled (Right-click → Properties → Account Tab).
✅ Verify that Jane is typing the correct username & password.
✅ Reset the password if needed (Right-click → Reset Password).
✅ Ensure Jane’s computer is connected to the domain (ping kevtech.com).
✅ If Jane gets “Trust relationship failed”, rejoin the PC to the domain (System Properties → Change → Rejoin domain).

🔹 Task 2: Map Network Drive for Jane Doe
👉 Objective: Ensure Jane can access her department's shared files.

✅ Instructions:

Check if the Marketing folder exists in Kevtech Shared Files
If not, create it: C:\Kevtech Shared Files\Marketing.
Set Folder Permissions
Right-click Marketing folder → Properties → Security
Add Marketing group with Modify permissions.
Share the Folder
Right-click Kevtech Shared Files → Properties → Sharing → Advanced Sharing
Check "Share this folder" and allow Read access for Everyone.
Map the Drive on Jane’s PC
Open Group Policy Management (gpmc.msc)
Go to User Configuration → Preferences → Drive Maps
Map \\SVR-01\Kevtech Shared Files\Marketing as a network drive.
📸 Proof Required: Screenshot of Jane accessing Marketing shared folder.

🚀 Troubleshooting Issue #2: Jane Can’t Access Shared Drive
🔎 Possible Causes & Fixes:
✅ Confirm Jane is in the Marketing security group (ADUC → Member Of).
✅ Check if Jane’s PC is on the same network as the server (ipconfig /all).
✅ Ensure the drive is mapped correctly (net use X: \\SVR-01\Kevtech Shared Files\Marketing).
✅ If Jane gets an access denied error, review folder permissions (Security Tab).
✅ Restart Workstation service (services.msc → Workstation → Restart).

🔹 Task 3: Configure Jane’s Email in Microsoft Outlook (Office 365)
👉 Objective: Set up Jane’s Microsoft Exchange email.

✅ Instructions:

Open Microsoft Outlook.
Click File → Add Account.
Enter Jane’s email: jdoe@kevtech.com.
Choose Microsoft Exchange as the server type.
Click Next, enter Jane’s network password, and complete setup.
📸 Proof Required: Screenshot of a test email sent from Jane’s Outlook.

🚀 Troubleshooting Issue #3: Jane Can’t Send or Receive Emails
🔎 Possible Causes & Fixes:
✅ Check if Jane’s email is enabled in Microsoft Exchange Admin Center.
✅ Ensure her Outlook profile is set correctly (Control Panel → Mail → Profiles).
✅ Verify autodiscover DNS record is set up (nslookup autodiscover.kevtech.com).
✅ Test login to webmail (https://outlook.office365.com) to confirm credentials.
✅ Run Microsoft Support and Recovery Assistant (SaRA) for Outlook issues.

🔹 Task 4: Install and Update Software on Jane’s PC
👉 Objective: Install required applications for Jane’s role.

✅ Instructions:

Install Office 365
Download from https://portal.office.com → Install.
Install Antivirus Software (Windows Defender or third-party)
Open Windows Security → Virus & Threat Protection.
Ensure Real-time Protection is on.
Install Google Chrome & Zoom for team meetings.
📸 Proof Required: Screenshot of installed apps from Control Panel → Programs & Features.

🚀 Troubleshooting Issue #4: Jane’s PC Is Running Slow After Installing Software
🔎 Possible Causes & Fixes:
✅ Check Task Manager (Ctrl + Shift + Esc) for high CPU/memory usage.
✅ Run Disk Cleanup (cleanmgr) to remove temp files.
✅ Disable unnecessary startup apps (msconfig → Startup).
✅ Check for Windows Updates (Settings → Update & Security).
✅ Upgrade RAM if hardware is insufficient (Check System Properties).

🔹 Task 5: Set Up Remote Assistance for Jane (Zoho Assist or Remote Desktop)
👉 Objective: Help Jane troubleshoot future issues remotely.

✅ Instructions:

Enable Remote Assistance on Jane’s PC
Go to Control Panel → System → Remote Settings.
Check "Allow Remote Assistance Connections".
Install Zoho Assist (Remote HelpDesk Tool)
Download from https://www.zoho.com/assist/ → Install.
Create a session and share the code with Jane to connect remotely.
📸 Proof Required: Screenshot of Zoho Assist session connected to Jane’s PC.

🚀 Troubleshooting Issue #5: Remote Connection Not Working
🔎 Possible Causes & Fixes:
✅ Ensure Jane’s PC is powered on and connected to the internet.
✅ Verify Remote Assistance is enabled on Jane’s computer.
✅ Check if firewall or antivirus is blocking remote connections.
✅ Restart Remote Desktop Services (services.msc → Restart RDP Service).

🎯 Final Review: Key Takeaways from the Scenario
✅ Created a new user account and assigned correct permissions.
✅ Mapped a shared network drive and tested access.
✅ Configured Microsoft Outlook for email.
✅ Installed required software and optimized performance.
✅ Set up Remote Assistance to support Jane remotely.

💡 Reflection Questions (Interview-Style)
How would you handle password reset requests for multiple users?
What steps would you take if multiple users report shared drive access issues?
How do you prioritize IT support tickets when several issues arise at once?
🚀 Pro Tip: Explaining your troubleshooting process clearly is just as important as solving the issue!

🔚 Conclusion: You’re Ready for the Real World!
By completing this scenario, you’ve demonstrated key HelpDesk Support skills that are crucial for IT roles. Would you like more practice scenarios or a mock interview Q&A? 😊








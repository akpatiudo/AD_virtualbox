## IT Support Technician – Network Setup Lab: An Interview Task For HelpDesk Support 

You are applying for a HelpDesk Support role at MedLabTech Company, and as part of your interview, the Network Administrator has assigned you a practical task. This task will test your ability to manage user accounts, shared network resources, and troubleshoot common issues.

## Task:
1. Use the table below to create the following staff user accounts, their respective departments are also  shown
  -  A user reports they can’t log in after you create their account. What steps would you take to resolve this?
2.  Create a Shared Network Drive
 Create a network drive called "MedLabTech shared files"  that is accessible to all users.
   -  Within it, create a  folder for each department that can only be  accessed by the members of each write to their  departments folder.
   -  Save a file and name it with the  chosen user name (user Snipping tool save evidence  of this on the Vm Host)
3. Rename Server to *"MED-SVR-01"* a domain controller for  the domain controller MedLabTech.com  

![image](https://github.com/user-attachments/assets/5280f73d-1cbc-4c2e-b69b-344e09e4a5c0)
![image](https://github.com/user-attachments/assets/9c0f44cd-5767-4c8d-b863-c5f753426d2e)

### *Task 1: Create User Accounts in Active Directory*
Instructions:
-  Open Active Directory Users and Computers (ADUC)
-  Press Win + R, type dsa.msc, and press Enter.
-  Create an Organizational Unit (OU) for "_Department"
-  Right-click on medlabtech.com → New → Organizational Unit.
-  Name it Department.
  - Create a Sales, HR, Finance OU Inside Departments
  - Epand medlabtech.com by clicking the + sign.
  - Right-click on Departments → Select New → Organizational Unit (OU)
  - Name it Sales → Click Ok do same for the rest 

### Add the Following Users to AD:
-  Department	User Full Name	Username
    -  Sales	Bob Smith	bsmith
    -  HR	Billy Banes	bbanes
    -  Finance	Holly Cross	hcross
-  Right-click on Sales → Select New → User
-  Fill in the details for Bob Smith: First Name: Bob, Last Name: Smith, User logon name: bsmith
-  Click Next
- Set a default password (e.g., P@ssw0rd123) Set a default password and enable 
- Check User must change password at next logon
- Click Next → Finish (repeat same for HR and Finance)
-  Proof: Take a screenshot of the users in ADUC.
-  ![](https://i.imgur.com/xKBA47p.png)
-  ![](https://i.imgur.com/xKBA47p.png)
-  ![](https://i.imgur.com/2c5swU7.png)

### Create Security Groups In Active Directory
-  Open Active Directory Users and Computers (ADUC) (Win + R → Type dsa.msc → Press Enter).
-   Navigate to your Staff Organizational Unit (OU) (medlabtech.com/Staff or medlabtech.com\Department) depending on your directory structure
-   Right-click on the Staff OU → Select New → Click Group.
-   Enter the group name based on the department, e.g.:
    -  Sales_Group. HR_Group, Finance_Group
        -  Under Group Scope, select Global.
        -  Under Group Type, select Security.
        -  Click OK.
Repeat this process for each department

###  Add Users To The Security Groups
-  Open ADUC (Win + R → Type dsa.msc → Press Enter).
-  Locate Bob Smith (bsmith) under Users.
-  Right-click Bob Smith → Click Properties.
-  Go to the Member Of tab → Click Add.
-  Type Sales_Group → Click Check Names → Click OK.
-   Click Apply → Click OK.
Repeat this for HR and Finance users, adding them to their respective groups.

### Task 2: Create a Shared Network Drive
-  Instructions:
-  Open File Explorer → Go to C:\ → Create a folder called Medlabtech Shared Files.
-  Create Department Folders Inside It:
  Sales, HR, Finance
-  Set Folder Permissions:
-  Right-click each folder → Properties → Security → Advanced.
-  Give Modify access to each department's users only
 ![](https://i.imgur.com/jAX2MoV.png)
-![](https://i.imgur.com/pxfFNZ9.png)

-  Share the Folder:
-  Right-click Medlabtech Shared Files → Properties → Sharing → Advanced Sharing.
-  Check "Share this folder" and allow Read access for Everyone.
📸 Proof: Save a test file in one of the department folders and take a screenshot.
- ![image](https://github.com/user-attachments/assets/e8b27376-0f25-4c4c-9d60-f74d67a6db1f)
-  ![](https://i.imgur.com/B9qKWtj.png)

### Map the Network Drive for Users
-  Open Group Policy Management (gpmc.msc)
-  navigate to: Forest → Domains → medlabtech.com
-  Expand your domain and look for the Group Policy Objects (GPOs) section.

 ### Create a new GPO: 
 -  Right-click Group Policy Objects → New.
-  Name it something like "Drive Mapping Policy".
-  Click OK, then Right-click the new GPO → Edit.
-  User Configuration → Preferences → Windows Settings → Drive Maps
- Right-click on "Drive Maps", then select New → Mapped Drive.
-  ![image](https://github.com/user-attachments/assets/263e2bfc-7473-4871-a6a2-24854e46f871)
-  ![image](https://github.com/user-attachments/assets/3b804f7b-1891-4de2-80c9-df599acb106f)
-  ![image](https://github.com/user-attachments/assets/fad3c9d2-ba19-4413-9bf8-07eb05518f8d)

 ####  Configure the Network Drive Mapping
In the New Drive Properties window, configure the following settings:
-  Action: Select Create.
-  Location: Type the full path of the shared folder, e.g.: \\medlabtech\medlabtech-sharefiles
-  Drive Letter: Choose a letter (e.g., Z:) from the dropdown.
-  Reconnect: Check this box to ensure the drive persists after reboots.
-  Label as (Optional): Enter a display name medlab
-  Click the Common tab and check:
-  Run in logged-on user’s security context (user policy option)
  (Ensures that the mapping applies to the user who logs in).
-  Click OK to save the settings.
-  ![image](https://github.com/user-attachments/assets/6a7bbee0-6c95-4f28-ad0f-58c9ada2015b)
-  ![image](https://github.com/user-attachments/assets/afa185fb-614f-4f47-9ae3-47f0c2835c58)
-  ![image](https://github.com/user-attachments/assets/70a9c425-0f23-4ec7-a21f-5079ae92929e)


### Link the GPO to the Correct Organizational Unit (OU)
Close the Group Policy Editor.
-  In Group Policy Management, right-click the OU containing the users (e.g., Departments).
-  Click Link an Existing GPO.
-  Select the GPO you just created (e.g., "Drive Mapping Policy") and click OK.

-  ![image](https://github.com/user-attachments/assets/2caad145-10f1-4263-a1db-8fbd61945f0b)
-  ![image](https://github.com/user-attachments/assets/4cd23c45-7147-4763-aff3-88fa1bfa2870)

### Force Group Policy Update on Client Machines
-  Press Win + R to open the Run dialog.
-  gpupdate /force
-  Using File Explorer (PowerShell Shortcut)
-   Open File Explorer (Win + E).
- Click the Address Bar and type:

powershell.exe gpupdate /force
![image](https://github.com/user-attachments/assets/f7149fff-6a91-45b9-8c0f-ee3e889c76a2)


### Task 3: Rename the Server and Set Up a Domain Controller
Instructions:
-  Right-click Start → System → Rename this PC.
-  Change the name to *MED-SVR-01*.
-  Restart the server.
![image](https://github.com/user-attachments/assets/d1a5ead4-dac4-41fc-9d2e-fcd5e2504947)
Restart the server when prompted.
📸 Proof: Take a screenshot of the Server Name and Domain Controller Status.
![image](https://github.com/user-attachments/assets/aa297b66-ac6c-4094-8544-537998981a40)

Join medlab-user-vm to the Domain
-  Login as admainuser and go to:
-  System → Advanced System Settings → Computer Name → Change
-  Enter Domain: medlabtech.com

Restart  medlabtech.com and log in 
Verify in ADUC that Client-1 appears under "Computers"
![image](https://github.com/user-attachments/assets/2f5ca3a8-9b76-4717-a044-88f351197de5)

### Apply Folder Permissions Using Security Groups
Now that security groups exist, modify folder permissions so that only the correct groups can access their department folders.
-  Open File Explorer (Win + E) and navigate to:
\\SVR-01\Medlabtech Shared Files
- Right-click the Sales folder → Select Properties.
- Go to the Security tab → Click Advanced.
- Click Disable Inheritance → Select Convert inherited permissions.
- Click Add → Click Select a Principal.
- Type Sales_Group → Click Check Names → Click OK.
- Set Permissions to Modify → Click OK → Apply
-  Repeat this for the HR and Finance folders, assigning the correct security group.

### Test Access Restrictions
-  Now, check if users can access the correct folders.
-  Log in as Bob Smith (Sales)
Open File Explorer → Go to Network → Open \\SVR-01\Kevtech Shared Files\Sales
Try to create and edit a file.
Try opening HR or Finance folders (you should be denied access).
Repeat for Billy Banes (HR) and Holly Cross (Finance).
📸 Proof: Take a screenshot showing access granted/denied.
![image](https://github.com/user-attachments/assets/649085ff-c5df-456f-996b-414f256409a8)
![image](https://github.com/user-attachments/assets/fc2d35a3-280d-465a-a1c3-1f18e1e71a91)
![image](https://github.com/user-attachments/assets/2b66bddd-2d87-48e8-b1e5-ba852a748c90)
![image](https://github.com/user-attachments/assets/f2087875-1873-47ad-a554-197ddd4f66f5)
![image](https://github.com/user-attachments/assets/d6535e4d-0e32-4b3b-8a19-9fd3d5f19824)
![image](https://github.com/user-attachments/assets/a1d115ca-7c6d-4cc6-836f-e26138e650b4)

### Why this task in iob Interview and of what importance therein to IT Support
1. Enhances IT Security – Ensuring users can only access authorized data reduces the risk of data breaches.
 
2. Streamlines User Management – Centralized user control simplifies onboarding and offboarding processes.
 
3. Improves IT Efficiency – Automation through GPOs minimizes repetitive tasks and configuration errors.
 
4. Supports Business Continuity – Proper access management ensures departments can function smoothly.
 
5. Prepares for Real-World IT Support – These skills are crucial for HelpDesk, System Administration, and IT Support roles.
 
This task demonstrates the core responsibilities of an IT Support Technician, showcasing expertise in user management, network administration, and security best practices. 

Thanks for your time 


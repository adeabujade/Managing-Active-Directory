<p align="center">
  
![image](https://github.com/user-attachments/assets/2242f440-7d95-4a4f-9bf3-b4b462d80442)

</p>

<h1>Active Directory Account Security Management</h1>
The objective of this project is to enhance the security, stability, and usability of user accounts within the organization’s Active Directory (AD) environment. This involves configuring account lockout policies to defend against unauthorized access, managing password resets, addressing unexpected account logouts, and proactively monitoring system logs to identify and respond to potential issues in real-time.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 Pro

<h2>Installation Steps</h2>

<h2>1. Setup the Group Policy Management Console </h2>

**1. Open up the Group Policy Management Console.**

    a. Right-click the Start Menu > Run 
  
    b. Run gpmc.msc
  
**2. Create or Edit a Group Policy Object (GPO)**
   
    a.Navigate to your domain or organizational unit (OU) where you want to apply the policy.
  
    b.Right-click and select Create a GPO in this domain, and Link it here, or select an existing GPO and click Edit.

**4. Navigate to Account Lockout Policy Settings**
   
    a. In the Group Policy Management Editor, go to:
  
    b. Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout Policy

**4. Configure the Three Key Settings**

    a. Account lockout threshold
      -Set the number of failed logon attempts allowed (Ex, 5 Invalid Attempts)
      
    b. Account lockout duration
      -Set how long (in minutes) the account will stay locked (Ex, 15).
      
    c. Reset the account lockout counter after
      -Set how long (in minutes) before the failed attempts counter resets (Ex, 15)

<img width="1463" height="838" alt="image" src="https://github.com/user-attachments/assets/74bb36c0-3178-41cd-9ec7-250a5a2480c2" />


**5. Apply and Close**

    a. You can wait for the Group Policy to take effect (90 minutes) or force an update.
  
    - On the client machine, open the command prompt and type gpupdate /force, then press Enter.


<h2>2. Dealing with Account Logouts </h2>

**1.Pick a user and attempt to log in 6 times with a bad password**


<img width="555" height="147" alt="image" src="https://github.com/user-attachments/assets/a4a75d82-e32a-4077-abe6-4c5a58f634e7" />

   
**2. Unlocking the account**
   
       a. Go to the Domain Controller and go to Active Directory Users and Computers
       b. Right-click mydomain.com and press Find
       c. Type the name of the user in the Name box
       d. Double click the user
       e. Go to the Account
       f. Check the Unlock Account box and then press Apply

 <img width="407" height="537" alt="image" src="https://github.com/user-attachments/assets/cdd3c03a-4b3d-4c82-9cd1-b3a376440c8e" />
   
**3. Re-login into the user account on the client**

<h2>2. Resetting Passwords </h2>

  **1. Reset Password**
  
      a. Go to Domain Controller and go to Active Directory Users and Computers
      b. Right-click mydomain.com and press Find
      c. Type the name of the user in the Name box
      d. Right-click the user and press Reset Password
      e. Type in new password
   
<img width="379" height="254" alt="image" src="https://github.com/user-attachments/assets/18b484f0-24c3-4d11-8fa3-7634214e7493" />

<h2>3. Disabling and Enabling Accounts </h2>

  **1. Disable Account**
  
      a. Go to the domain Controller and go to Active Directory Users and Computers
      b. Right-click mydomain.com and press Find
      c. Type the name of the user in the Name box
      d. Right-click the user and press Disable Account

<img width="557" height="125" alt="image" src="https://github.com/user-attachments/assets/44a47c9c-0c7f-416e-92c3-72f1eed7aaca" />

  **2. Enable Account**
  
      a. Go to the domain Controller and go to Active Directory Users and Computers
      b. Right-click mydomain.com and press Find
      c. Type the name of the user in the Name box
      d. Right-click the user and press Enable Account

<h2>4. Observing Logs </h2>

  **1. Observing Logs as the Domain Controller**
    
         a. Type into the search box eventvwr.msc and press Enter 
         b. Go into Windows Logs > Security
         c. To find logs for a particular account, right-click Security, press Find, and type in the particular user

  <img width="1560" height="947" alt="image" src="https://github.com/user-attachments/assets/656ffb7c-a72d-43c8-9fa3-a7fc0fd3c723" />

     
  **2. Observing Logs as the Client**
  
       a. Type into the search box eventvwr.msc and run it as an administrator
       b. Type in Admin Credentials
       c. Go into Windows Logs > Security
       d. To find logs for a particular account, right-click Security, press Find, and type in the particular user

<img width="1564" height="944" alt="image" src="https://github.com/user-attachments/assets/3466d848-e12d-4e88-be0b-54da9604b612" />




















  

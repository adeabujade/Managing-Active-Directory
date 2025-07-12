<p align="center">
  
![image](https://github.com/user-attachments/assets/2242f440-7d95-4a4f-9bf3-b4b462d80442)

</p>

<h1>Resetting Passwords with Active Directory</h1>
The primary objective of this project is to establish a secure, efficient, and standardized procedure for managing user password resets within an Active Directory environment. This process aims to minimize user downtime, maintain the integrity of user accounts, and uphold organizational security policies. By leveraging Active Directory Users and Computers (ADUC), the goal is to ensure that all password reset requests are handled promptly and accurately, with proper verification and documentation.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 Pro

<h2>Installation Steps</h2>

<h2>1. Setup the Group Policy  </h2>

1. Open up Group Policy Management Console.
   
  a. Right-Click the Start Menu > Run 
  b. Run gpmc.msc
  
2. Create or Edit a Group Policy Object (GPO):
  a.Navigate to your domain or organizational unit (OU) where you want to apply the policy.
  b.Right-click and select Create a GPO in this domain, and Link it here, or select an existing GPO and click Edit.

3. Navigate to Account Lockout Policy Settings:
   
  a. In the Group Policy Management Editor, go to:
  b. Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout Policy

4. Configure the Three Key Settings:

  a. Account lockout threshold
    -Set the number of failed logon attempts allowed (Ex. 5 Invalid Attempts)
  b. Account lockout duration
    -Set how long (in minutes) the account will stay locked (Ex. 15).
  c. Reset account lockout counter after
    -Set how long (in minutes) before the failed attempts counter resets (Ex. 15)

<img width="1463" height="838" alt="image" src="https://github.com/user-attachments/assets/74bb36c0-3178-41cd-9ec7-250a5a2480c2" />


5. Apply and Close:

  a. You can wait for the Group Policy to take affect (90 minutes) or force an update.
  
    - On the client machine, open command prompt and type gpupdate /force then press enter.


<h2>2. Dealing with Account Logouts  (DC-1) in Azure</h2>

































  

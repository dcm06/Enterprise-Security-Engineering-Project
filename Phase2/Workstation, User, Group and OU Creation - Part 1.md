## PHASE2 - PART 1: Workstation, User, Group and OU Creation

In this Phase, I will be setting up the two workstations L-PC1, and L-PC2 in their respective subnets, then joining them to the domain. After, Organizational Units will be created, then Groups, and then workstations and User locations will be modified.


### Renaming the PAW
---
 <img width="975" height="566" alt="image" src="https://github.com/user-attachments/assets/b184ed23-9d31-4f19-a2ef-9ca89bdd9196" />


Joined to the Domain
 


 

Renaming and joining the standard workstations to the domain
Renaming Both workstations to L-PC1 and L-PC2 respectively
 

 



Network Properties and Pings for PC1 and PC2

 

 

Joining Both PCs to the Domain



Test User login after Restart
 
Installing RSAT tools for remote management of the server
 
 
 

SETTING UP Ous

London Branch
 

 
Moving PCs to the right OUs to enable GP Management of Devices
 
 

 
 


 
Groups Creations
-	Department / User Groups (4 groups)
 
These are your core identity + access groups:
•	HR_Users
•	Finance_Users
•	IT_Users
•	Sales_Users
👉 Covers: file access, folder permissions, GPO targeting



Admin / IT Control Groups (3 groups)
 
-	These let you demonstrate delegation + restricted admin roles:
•	Server_Admins
•	Helpdesk_Tier1


Security Policy control groups
 
•	USB_Restricted_Users
•	Local_Admin_Workstations
•	Password_Strong_Policy_Users
👉 Covers: security enforcement, device control, policy filtering


Resource Access Groups (2 groups)
 
For file shares + printers:
•	HR_File_Access
•	IT_File_Access
👉 Covers: NTFS permissions + shared drives



Moving created users to their respective Ous
 





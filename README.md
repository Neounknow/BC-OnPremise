**Command for BC on Premise**
Import lib
>."C:\Program Files\Microsoft Dynamics 365 Business Central\180\Service\NavAdminTool.ps1"

Create User Demo
> $Password = (Read-Host "Enter password" -AsSecureString)
> 
> New-NAVServerUser -ServerInstance BC183 -UserName demo -LicenseType Full -State Enabled -Password $Password
> 
> New-NAVServerUserPermissionSet -PermissionSetId SUPER -ServerInstance BC183 -UserName demo

**Setup NavUserPassword**
1. Add User in previous topic
2. Change Credential Type to NavUserPassword
3. Fill Certificate Thumbprint from mmc.exe -> certificate -> your cerfiticate -> properties -> thumprint
4. Restart BC Service
5. Open navsetting.json on wwwroot/BC
6. Change ClientServiceCredentialType to NavUserPassword
7. Restart Website

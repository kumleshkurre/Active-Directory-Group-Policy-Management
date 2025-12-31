## //------------- Top 5 Group Policy (GPO) – AD DS Server ----------------//

1. Map Network Drive to Clients using GPO

Step 1: Folder Sharing on Server
go file explorer  
go your drive like:- D drive  
right click on D drive  
properties  
sharing  
advanced sharing  
tick:- share this folder  
permissions  
allow:- full control  
apply and ok  

copy network path  
win-62QTLAIRTKE\kurre  

Step 2: Create GPO
go server manager  
tools  
group policy management  
go domains → kurrecomputers.local  
right click OU:- Raipur  
create a GPO in this domain  
new GPO  
rename GPO like:- Policy 

Step 3: Configure Drive Mapping
right click GPO:- Policy 
edit  
user configuration  
preferences  
windows settings  
drive maps  
right click → new → mapped drive  

action:- create  
location:- \\10.0.0.1\kurre  
drive letter:- D  
tick:- show this drive  
tick:- show all drives  
apply and ok  

client should show network drive  

//----------------------------------------------------------------------//

2. Control Panel Block using GPO

right click GPO:- Policy 
edit  
user configuration  
policies  
administrative templates  
control panel  
double click:- prohibit access to control panel and pc settings  
enable  
apply and ok  

//----------------------------------------------------------------------//

3. Set Fixed Desktop Wallpaper using GPO

copy wallpaper file to shared drive  
give read permission to users  

right click GPO:- Policy 
edit  
user configuration  
policies  
administrative templates  
desktop  
desktop  
desktop wallpaper  
enable  

paste wallpaper path like:-  
\\10.0.0.1\kurre\wallpaper.jpg  

apply and ok  

//----------------------------------------------------------------------//

4. Hide / Remove Recycle Bin Icon from Desktop

right click GPO:- Policy 
edit  
user configuration  
policies  
administrative templates  
desktop  
double click:- remove recycle bin icon from desktop  
enable  
apply and ok  

//----------------------------------------------------------------------//

5. Block USB / Removable Storage Access

right click GPO:- Policy 
edit  
computer configuration  
policies  
administrative templates  
system  
removable storage access  
double click:- all removable storage classes deny all access  
enable  
apply and ok  

//----------------------------------------------------------------------//

After all configuration completed

go client pc  
press windows + R  
type:- gpupdate  
press enter  

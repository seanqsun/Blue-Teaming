# irsec checklist
**Harden that fuuuucckkkk outta that Windows**  
1. Access Control
- Disable/remove non user accounts  
  * lusrmgr.msc
  * Disable default admin and guest accounts
- Establish another admin account and set main account to limited
  * Add new admin to admin local group
  * Rename default administrator and guest accounts. They represent a security risk because apparently knowing the names is the first step to hacking it remotely.
- Require Ctrl-Alt-Del for elevation
 * Local Group Policy Editor > Computer Configuration > Administrative Templates > Windows Components > Credential User Interface
 * Require trusted path for credential entry > Enable that shit  

2. Application Security
3. Network Security

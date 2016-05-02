# hardening
###Harden that fuuuucckkkk outta that Windows###
**Access Control**
- Disable/remove non user accounts  
  * lusrmgr.msc
  * Disable default admin and guest accounts
- Establish another admin account and set main account to limited
  * Add new admin to admin local group
  * Rename default administrator and guest accounts. They represent a security risk because apparently knowing the names is the first step to hacking it remotely.
- Require Ctrl-Alt-Del for elevation
 * Local Group Policy Editor gpedit.msc
 * Computer Configuration > Administrative Templates > Windows Components > Credential User Interface
 * Require trusted path for credential entry > Enable that shit

**Application Security**
- Applocker is bae
  * Local Group Policy Editor gpedit.msc
  * Computer Configuration > Window Settings > Security Settings > Application Control Policies
  * Allow/Deny access so bad guys don't fux wit us
- The sidepiece, EMET
  * https://support.microsoft.com/en-us/kb/2458544
  * Run it, configure system
  * DEP is set to always enabled
  * SEHOP is set to opt-out
  * ASLR is opt in enabled
  * Add applications through "Configure Apps"
 

**Network Security**
- Disable IPv6
- Firewall

**Moar Group Policy Editor**
- Computer Configuration\Windows Settings\Security Settings\Account Policies\Password Policy\ 
  * Pwd length min = 15
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\ 
  * Interactive logon: Do not display last user name = enabled 
  * User Account Control: Virtualize file and registry write failures to per-user locations = enabled 
  * User Account Control: Only elevate UIAccess applications that are installed in secure locations = enabled
  * User Account Control: Behavior of the elevation prompt for standard users = prompt for credentials on the secure desktop 
  * User Account Control: Behavior of the elevation prompt for administrators in Admin Approval Mode = prompt for consent on the secure desktop
  * MSS: (SafeDllSearchMode) Enable Safe DLL search mode (recommended) = enabled 
  * Shutdown: Allow system to be shut down without having to log on = enabled 
  * Interactive logon: Do not require CTRL+ALT+DEL = disabled 
- Computer Configuration\Windows Settings\Security Settings\Local Policies\User Rights Assignment\ 
  * Bypass traverse checking = Users,Network Service,Local Service,Administrators 
  * Allow log on locally = Administrators, Users
- Computer Configuration\Administrative Templates\Windows Components\Credential User Interface\ 
  * Require trusted path for credential entry = enabled
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\Interactive logon: Do not require CTRL+ALT+DEL
  * disable that shit
- Computer Configuration\Administrative Templates\Windows Components\NetMeeting\ 
  * Disable remote Desktop Sharing = enabled
- Computer Configuration\Administrative Templates\Network\Microsoft Peer-to-Peer Networking Services\ 
  * Turn off Microsoft Peer-to-Peer Networking Services = enabled
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\Accounts: Guest account status
  * Accounts: Guest account status = Disabled
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\Accounts: Rename administrator account
  * Accounts: Rename administrator account = Not Defined
  * Accounts: Rename guest account = Not Defined
- Computer Configuration\Administrative Templates\System\Remote Assistance\ 
  * Solicited Remote Assistance = disabled
- Computer Configuration\Administrative Templates\Windows Components\HomeGroup\ 
  * Prevent the computer from joining a homegroup = enabled
- Computer Configuration\Windows Settings\Security Settings\Windows Firewall with Advanced Security\Windows Firewall with Advanced Security\Windows Firewall Properties\Public Profile\ 
  * Windows Firewall: Public: Allow unicast response = No
- User Configuration\Administrative Templates\Control Panel\Personalization\ 
  * Password protect the screen saver = enabled
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\MSS: (ScreenSaverGracePeriod) The time in seconds before the screen saver grace period expires (0 recommended)
  * MSS: (ScreenSaverGracePeriod) The time in seconds before the screen saver grace period expires (0 recommended) = 0
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\Interactive logon: Display user information when the session is locked
  * Interactive logon: Display user information when the session is locked = Enable
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\System cryptography: Force strong key protection for user keys stored on the compute
  * System cryptography: Force strong key protection for user keys stored on the computer = Enable
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\User Account Control: Behavior of the elevation prompt for standard users
  * User Account Control: Behavior of the elevation prompt for standard users = Automatically deny elevation requests
- Computer Configuration\Administrative Templates\Windows Components\Windows Installer\Always install with elevated privileges
  * Always install with elevated privileges = Disabled
- Computer Configuration\Administrative Templates\System\Internet Communication Management\Internet Communication settings\Turn off downloading of print drivers over HTTP
  * Turn off downloading of print drivers over HTTP = Enabled
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\Network access: Do not allow anonymous enumeration of SAM accounts and shares
  * Network access: Do not allow anonymous enumeration of SAM accounts and shares = Enabled
- Computer Configuration\Windows Settings\Security Settings\Local Policies\Security Options\Shutdown: Clear virtual memory pagefile
  * Shutdown: Clear virtual memory pagefile = Enable

**Logs to consider turning off**
- Audit Policy: System: Other System Events = No Auditing
- Audit Policy: Logon-Logoff: Logon = No Auditing
- Audit Policy: System: Security State Change = No Auditing
- Audit Policy: Logon-Logoff: Special Logon = No Auditing
- Audit Policy: System: System Integrity = No Auditing
- Audit Policy: Account Management: Security Group Management = No auditing
- Audit Policy: Logon-Logoff: Account Lockout = No auditing
- Audit Policy: Policy Change: Audit Policy Change = No auditing
- Audit Policy: Policy Change: Authentication Policy Change = No auditing
- Audit Policy: Logon-Logoff: Logoff= No auditing



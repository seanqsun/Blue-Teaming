# Checklist/Roles
-Chrooting: https://www.digitalocean.com/community/tutorials/how-to-configure-chroot-environments-for-testing-on-an-ubuntu-12-04-vps and https://help.ubuntu.com/community/BasicChroot
- Blue team tools (Thank you Jaime)
 * IDS/IPS
 * https://sourceforge.net/projects/smoothsec/ and https://ossec.github.io/downloads.html
 * nmap. scan yoself
   * cheatsheet: https://highon.coffee/blog/nmap-cheat-sheet/
 * AntiVirus
    * vast: https://www.avast.com/en-us/index
- Make Windows so safe
  * 10.10.x.110
  * See hardening.md
  * http://www.blackviper.com/service-configurations/black-vipers-windows-7-service-pack-1-service-configurations/
- Cisco Router
 * Idk man, acl rules or something.
 * Maybe we should encrypt the data. that would be cool.
 * https://www.cisco.com/c/en/us/td/docs/ios/12_2/security/configuration/guide/fsecur_c/scfpass.html
- Windows Server: AD, DNS
  * 10.10.x.10
  * Follow along lol
  * http://www.antimidas.net/index.php/articles/technology/575-lock-down-active-directory-in-10-steps 
  * https://support.rackspace.com/how-to/installing-active-directory-domain-services-on-windows-server-2008-r2-enterprise-64-bit/
- Windows Server Exchange/Mail
  * 10.10.x.20
  * **This takes forever to install, do this early on** > https://technet.microsoft.com/en-us/library/bb124778(v=exchg.160).aspx
- Ubuntu/Debian: SSH, MySQl, DNS
  * 10.10.x.30
  * Secure the shit outta your ubuntu: http://blog.internot.info/2014/06/securing-ubuntu-desktop-from-bad-guys.html
  * SSH: https://help.ubuntu.com/lts/serverguide/openssh-server.html
  * SSH.2: https://help.ubuntu.com/community/SSH/OpenSSH/Configuring
  * MySQL: https://help.ubuntu.com/12.04/serverguide/mysql.html
  * DNS: https://www.digitalocean.com/community/tutorials/how-to-configure-bind-as-a-private-network-dns-server-on-ubuntu-14-04
- Fedora 22: HTTP, FTP
  * 10.10.x.40
  * Inital Setup > https://www.digitalocean.com/community/tutorials/initial-setup-of-a-fedora-22-server
  * HTTP> https://docs.fedoraproject.org/en-US/Fedora/22/html/System_Administrators_Guide/ch-Web_Servers.html
  * FTP > vsftpd > https://www.liquidweb.com/kb/how-to-install-and-configure-vsftpd-on-fedora-22/
- Incidence Response
 * See ir form
- Misc
 * Pls no rmrf: https://lambdaops.com/rm-rf-remains/



## OpenAudit Software Installation Guidance 
 
### What is open-audit and how does it work?

Open-AudIT is an application to tell you exactly what is on your network, how it is configured and when it changes. Most organizations cannot give accurate location data of their assets, Open-AudIT gives you this information in seconds. Open-AudIT intelligently scans an organization’s network and stores the configurations of the discovered devices.
 
### How does open-audit work?

The script gathers extensive information and sends it back to the Open-AudIT server. If the device is a switch, router, printer, etc and it has SNMP enabled and Open-AudIT has working credentials, its attributes will be queried using SNMP and no audit scripts will be used. Once the data is in Open-AudIT, it is yours to query at will.
 
### Compatibility

Windows download is not compatible with Windows 10.
* Opmantek uses and recommends Windows Server 2016. 
* All downloads are for 64bit systems only.
* Most suitable installation in Cento , Ubuntu and window server 2016 is recommended. Other than these mentioned operating systems it is very difficult to handle installation. 

### Installation Procedure 

A lot of confusion regarding installation of OpenAudit,  but I have explained the very simple procedure of installing openAudit in chronological order in the terminal of a linux operating system such as Ubuntu.  
 
     sudo -i
     
 
     mkdir openAuditIt
     
 
     cd openAuditIT
     
 
     wget https://dl-openaudit.opmantek.com/OAE-Linux-x86_64-release_4.3.3.run
     
 
     chmod u+x ./OAE-Linux-x86_64-release_4.3.3.run
     
 
     sudo sh ./OAE-Linux-x86_64-release_4.3.3.run
 
 
The following instructions are given during the phase of installation. 
 
* Ok to proceed with installation:y

* Do you want to install these packages with APT now?: Y  | Auto instal  all missing packets
 
* Type 'Y" or <Enter> to accept, or 'n' decline:y
  
* Ok install the init script for the Opmantek daemon?:y
  
* Ok install the updated logrotate config file omk-rotate.conf?:y
  
* Do you want to import any new configuration settings now?
  
* Hit <Enter> when ready to continue:press enter
  
* Ok to install the updated Apache proxy config file?:y
  
* Ok to install new License Refresh cron schedule?:y
  
* Should I set the default open-Audit root password"openauditrootuserpassword'?:y
  
* Ok to install new open-Audit cron schedule?:y
  
* Would you like to see an overview of all changed configuration items?:y
  
* You should review those differences (using less or an editor like nano, Vi or emacs) and adjust your configuration settings accordingly:enter
  
* Do you want to start the Opmantek daemon now?:y
 
#### Compeleted Installation and read to open OpenAuditIT interface on browser. 


The following instructions are written in the snapshot below in order to open the interface in browser for ready to excess interface of OpenAudit  and password by default are username : admin and password : password. 
  
Type on Browser:  http://<IP address>:8042/en/omk/open-audit/login

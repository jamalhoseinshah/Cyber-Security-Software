### OpenAudit Software Installation Guidance 
 
### What is open-audit and how does it work?

Open-AudIT is an application to tell you exactly what is on your network, how it is configured and when it changes. Most organizations cannot give accurate location data of their assets, Open-AudIT gives you this information in seconds. Open-AudIT intelligently scans an organization’s network and stores the configurations of the discovered devices.
 
### How does open-audit work?

The script gathers extensive information and sends it back to the Open-AudIT server. If the device is a switch, router, printer, etc and it has SNMP enabled and Open-AudIT has working credentials, its attributes will be queried using SNMP and no audit scripts will be used. Once the data is in Open-AudIT, it is yours to query at will.
 
### Compatibility

* Windows download is not compatible with Windows 10.
* Opmantek uses and recommends Windows Server 2016. 
* All downloads are for 64bit systems only.
* Most suitable installation in Cento , Ubuntu and window server 2016 is recommended. Other than these mentioned operating systems it is very difficult to handle installation. 

### Installation Procedure 

A lot of confusion regarding installation of OpenAudit,  but I have explained the very simple procedure of installing openAudit in chronological order in the terminal of a linux operating system such as Ubuntu.  
 
 Entering to root 
 
       sudo -i
     
 Make a Directory named as OpenAuditIT
 
       mkdir openAuditIt
     
 Move to OpenAuditIT directory
 
       cd openAuditIT
     
 Start Installation OpenAuditIT it will direct install from Website.
 
 
       wget https://dl-openaudit.opmantek.com/OAE-Linux-x86_64-release_4.3.3.run
       
     
chmod +x file.run gives the file the execute permission but it does not control whose permissions the file has when it executes. ./file.run runs the file with the privileges of your user. sudo ./file.run runs the file with the privileges of root. Your file.run apparently needs root privileges.
     
       chmod u+x ./OAE-Linux-x86_64-release_4.3.3.run
     
Go to open-audit.organd download the latest version. Supply your name, email and company and download the binary. Run “sudo ./OAE-Linux-x86_64-release_2.0.11.run”. Log on to Open-AudIT and you should see a splash screen informing you that you do not have a license – but Opmantek will give you a 20 device license for free
     
 
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
 
 ![Screenshot from 2022-08-13 02-50-13](https://user-images.githubusercontent.com/95676591/184525428-043014fc-fdcc-4b53-b0b2-a6bdbd408414.png)

![Screenshot from 2022-08-13 04-01-12](https://user-images.githubusercontent.com/95676591/184525651-e195ef68-3b02-4b49-90e1-0ff4e4feb097.png)
 
 ![Screenshot from 2022-08-13 03-59-42](https://user-images.githubusercontent.com/95676591/184525676-2883e3aa-7907-4a84-ab57-154cbf55ed98.png)


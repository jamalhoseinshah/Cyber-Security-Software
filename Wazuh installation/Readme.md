This was created by Jamal Hussain Shah in order to facilitate others' quick installation of WAZUH without wasting time.

![images](https://user-images.githubusercontent.com/95676591/184079613-11fe0edc-93ca-4ef5-95c7-7fc8c46076fc.png)

## Wazuh 

Wazuh is a free, open source and enterprise-ready security monitoring solution for threat detection, integrity monitoring, incident response and compliance.
Wazuh Manager Installation guide

The most convenient way of installing wazuh manager  is on a VM. Let us describe the chronological order below. 

## Virtual Machine (OVA)

Wazuh provides a pre-built virtual machine image in Open Virtual Appliance (OVA) format. This can be directly imported to VirtualBox or other OVA compatible virtualization systems. Take into account that this VM only runs on 64-bit systems. It does not provide high availability and scalability out of the box. However, these can be implemented by using distributed deployment.

Download the virtual appliance (OVA), which contains the following components:
CentOS 7
Wazuh manager 4.3.6
Wazuh indexer 4.3.6
Filebeat-OSS 7.10.2
Wazuh dashboard 4.3.6

## Downloads:
Link for download Virtual Machine (OVA) - Installation alternatives
Secondly, You are required to use a Virtual Machine so therefore, download the link below. https://www.virtualbox.org/wiki/Downloads

## Setting on Virtualbox
You are required to change settings in the Virtual box like on the network option select  Bridge Adaptor.
On the virtualbox Storage option select the location where you have a download file named as Opmantek-20220130-VM9-Centos 7.2009-64 bit.
On the virtualbox start option in order to begin installation. 


Once installation is completed, username and password will appear on the screen. 
By default, the username is wazuh-user and password wazuh. 

![1_ntmV4oYMjMJRxh2fV8P5dQ](https://user-images.githubusercontent.com/95676591/184076582-8fb887bf-e10a-4440-925c-70930b3c801b.png)

In order to find an ip address you will type ip add on terminal . It will show an ip address and when you open the browser type this ip address you will see wazuh interface begins.

![1 0rDWTTESZ3VHgdlIpJtL4Q](https://user-images.githubusercontent.com/95676591/184076644-963eb974-6687-48a1-975f-9db693c690dd.png)

By default, login user name is admin and password is admin. 

Windows 10 Operating system, the antivirus protection that comes installed with the device is your default security app.

Important: Windows operating systems are embedded with a lot of security, which creates problems for opening, but if you open this IP on a Linux machine, it will open without any error.

![p6-1024x533](https://user-images.githubusercontent.com/95676591/184076780-b8012ca3-db6f-4cbc-abeb-eceb931f4c53.png)

## Installation of Wazuh agent 
The Wazuh agent is multi-platform and runs on the hosts that the user wants to monitor. It communicates with the Wazuh manager, sending data in near real time through an encrypted and authenticated channel.

##Important:
Easiest way to install wazuh agent  on Debian systems because the window  platform shows errors and is difficult to handle for beginers.  
 
how to install Wazuh agents on Ubuntu/Debian systems. Wazuh operates in server-client architecture. It is made up of a Wazuh server and Wazuh agents.
Wazuh agents collect data from the end-points and ship it to the Wazuh manager for processing. It is capable of;

* Log and data collection
* File integrity monitoring
* Rootkit and malware detection
* Security policy monitoring.
* Configuration assessments
* Software inventor

## Easy Way to Install Wazuh Agents on Ubuntu/Debian
Wazuh agent can be installed on various platforms including AIX, HP-UX, Solaris, Windows systems. However, this tutorial focuses on how to install Wazuh agents on Ubuntu/Debian Linux systems.

Install Wazuh Agents on Ubuntu/Debian
Wazuh provides APT repositories which makes it easy to install Wazuh agents on Ubuntu/Debian systems.

Therefore, to use Wazuh APT repos to install Wazuh agents on Ubuntu/Debian system:

Install Repository GPG signing Key
      
       apt install curl
       curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | apt-key add -

Add Wazuh repository:
      
       echo "deb https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list

Update system package cache:
      
       apt update

Install Wazuh Agents on Ubuntu/Debian

Now that the repos are set, you can proceed to install Wazuh agents. However, there are two options here Install and manually register the agent
So if you need to install the agent and later add it to the server for manual registration, simply run the command below to install it;

      apt install wazuh-agent
    
If you choose to install the Wazuh agent this way, then you need to add the agent to the server by running the command below (on the server where the agent is installed)

     /var/ossec/bin/agent-auth -m MANAGER-IP [-A AGENT_NAME]

To register the agent with the automatic system hostname name just omit the [-A AGENT_NAME].
However, before you can proceed, ensure you can connect to the Wazuh-manager registration ports 1515/TCP. Ensure that this port is open on the firewall, if any is running.
    
   
     telnet 192.168.59.17 1515
     Trying 192.168.59.17...
     Connected to 192.168.59.17.
     Escape character is '^]'.
   
     /var/ossec/bin/agent-auth -m 192.168.59.17
   
Next, set the Wazuh server IP in the Wazuh configuration file, /var/ossec/etc/ossec.conf.

Simple replace MANAGER_IP with the IP address;

     sed -i 's/MANAGER_IP/192.168.59.17/' /var/ossec/etc/ossec.conf

Install and automatically register Wazuh agent

To install and automatically register your Wazuh agent, execute the command below. Replace the Wazuh-manager IP accordingly.

     WAZUH_MANAGER="192.168.59.17" apt install wazuh-agent
 
You can also download the installation command to automatically enroll the agent right from the Wazuh manager agents dashboard.
Navigate to Wazuh App > Agents > Deploy new agent and follow the procedure.

## Running Wazuh Agent

Once the agents are installed and registered, start and enable the agents to run on system boot:
Before that, you need to know that by default, Wazuh expects the agent to communicate with it through 1514/TCP.
Hence, ensure that this port is opened on the Wazuh server if the firewall is running.

     systemctl enable --now wazuh-agent.service

Be sure to check the logs;

     tail -f /var/ossec/logs/ossec.log

Check Wazuh Agents Status
Verify that the agents are now connected to the server and active;

     /var/ossec/bin/agent_control -l

You can also verify from the Wazuh interface. Wondering how? See our guide on integrating Wazuh Server with ELK stack.


![p6-1024x533](https://user-images.githubusercontent.com/95676591/184076912-f1fcb494-60a1-4f56-96bb-2e5c4cf8eb08.png)




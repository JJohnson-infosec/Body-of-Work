# Body-of-Work
UCB Cybersecurity Works 

#view in RaW to avoid formatting errors!!


Automated ELK Stack =Deployment
The files in this repository were used to configure the network depicted below.
https://github.com/JJohnson-infosec/Body-of-Work.git

These  files  have  been  tested  and  used  to  generate  a  live  ELK  deployment  on Azure.  
They  can  be  used  to  either  recreate  the  entire  deployment  pictured  above. Alternatively, 
 select  portions  of  the  Project-1  file  may  be  used  to  install  only certain pieces of it, 
such as Filebeat.

•  ELK_config.yml

This document contains the following details:  - Description of the Topologu - Access Policies - 
ELK Configuration - Beats in Use - Machines Being Monitored
- How to Use the Ansible Build

Description  of  the  Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the 
D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly available, in addition to restricting 
inbound to the network.  Load  Balancers  main  purpose  is  to manage  traffic,  this  can  help  
secure  that  our  data  is  accessible  and  that  our servers  are  protected  against  
cyberthreats  that  wish  to  disrupt  our  flow  of  data IE)DDoS  attacks.   Jumpboxes protect 
our servers from being exposed to the public.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the VM's 
on Network and system files.  Filebeat
The configuration details of each machine may be found below.



Name            Function    IP Address    Operating System 
Jump Box      Gateway    10.0.0.1            Linux
DVWA1         Web Server  10.0.0.7           Linux
DVWA2         Web Server  10.0.0.8           Linux 
ELK           Monitoring  10.1.0.4           Linux

Access Policies
The machines on the internal network are not exposed to the public Internet.
Only  the  Jump  Box  machine  can  accept  connections  from  the  Internet. Access to this 
machine is only allowed from the following IP addresses:  - 24.130.111.70



Machines within the network can only be accessed by each other.  - DVWA1 and DVWA 2 send traffic to 
ELK server.
A summary of the access policies in place can be found in the table below.
Name           Publicly Accessible    Allowed IP Addresses 
Jump Box        Yes                                      24.130.111.70
ELK             No                                       10.1.0.4
DVWA            No                                       10.0.0.7
DVWA            No                                       10.0.0.8
Elk  Configuration
Ansible was used to automate configuration of the ELK machine.  No configura-tion was  performed  
manually,  which  is  advantageous  because. . .   It  creates  consistency  is
configuration management .
The playbook implements the following tasks:  -
•   First, ssh into our Jump-Box using "ssh username@jumpbox.ip
•   Check your Ansible container - "$ sudo docker ps"
•   Locate container name -"$ sudo docker container list -a"
•   Start Container - "$ sudo docker container start <docker_name>"
•   Connect to the Ansible container- "$ sudo docker container attach <docker_name>"
•   Copy our ssh key from Ansible container - "# cat -/.ssh/id_rsa.pub"
Then we configure our new machine using this SSH key and our " Yml" playbook

The following screenshot displays the result of running docker ps after success-fully configuring 
the ELK instance.
The following image link needs to be updated.   Screen  Shots  can  be  found  at  link  :

https://github.com/JJohnson-infosec/Body-of-Work.git

Target  Machines  &  Beats
This ELK server is configured to monitor the following machines:  -
Web Server  10.0.0.7                    Web Server  10.0.0.8
We have installed the following Beats on these machines:  - Filebeat - Metricbeat
These  Beats  allow  us  to  collect  the  following  information  from  each  machine: Filebeat  
monitors  the  log  files  or  locations  that  you  specify,  collects  log  events,  and forwards 
them either to Elasticsearch or Logstash for indexing. And Metricbeat takes the metrics and 
statistics that it collects and ships them to the output that you specify, such as
Elasticsearch or Logstash.

https://github.com/JJohnson-infosec/Body-of-Work.git

Using  the  Playbook
In order to use the playbook, you will need to have an Ansible control node already configured.  
Assuming you have such a control node provisioned:
SSH  into  the  control  node  and  follow  the  steps  below:  -  Copy  the  Playbook  file to 
Ansible  Control  Node.  - Update the Config file to include. . .  WEBSERVER  IP  / accessible     
PORTS     ,-    Run    the    playbook    by    using    the    following    cmd    " 
#ansible-playbook <name>.yml , and navigate to HTML to check that the installation worked as 
expected.



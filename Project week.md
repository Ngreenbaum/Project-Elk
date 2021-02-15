## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

Elk_Stack_Project_Diagram: https://github.com/Ngreenbaum/Project-Elk/blob/main/Diagrams/Elk%20Stack%20Project.jpg

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  - 

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, full redundancy therefore providing full performance at all times. The load balancer distributes network traffic across the multiple servers to ensure availability and redundancy. In addition to restricting all traffic but peer network traffic.  
The Load Balancer plays an important role by defending an organization against DDos Attacks. It does this by shifting traffic the corporate server to the public cloud providor. The advantage of having a Jump Box is providing a gateway to your virtual network.

Integrating an ELK server allows users to aggregate logs from all of your systems and applications, analyze these logs, and creat visualizations for application and infrastrcuture monitoring, faster troubleshooting, and security analyticss.
- Filebeat specifies log files and monitors events.


The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |

| Jumpbox 	| 10.0.0.4 	| Gateway                         	| Linux 	|   	|
|---------	|----------	|---------------------------------	|-------	|---	|
| Web1    	| 10.0.0.5 	| Webserver                       	| Linux 	|   	|
| Web2    	| 10.0.0.6 	| Webserver                       	| Linux 	|   	|
| Elk VM  	| 10.1.0.4 	| Elastic Stack Monitoring Server 	| Linux 	|   	|


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 32.213.7.21

Machines within the network can only be accessed by Jumpbox and then the private IP  Web 1 10.0.0.5 amd Web2 10.0.0.6.
- _TODO: I allowed access from my webservers- web 1 and web 2 in to y Elk Machine. 

A summary of the access policies in place can be found in the table below.
| Name    	| Publicly Available? 	| Allowed IP Addresses                          	|   	|
|---------	|---------------------	|-----------------------------------------------	|---	|
| Jumpbox 	| Yes                 	| 32.213.7.21                                   	|   	|
| Web1    	| No                  	| 40.87.91.168; 10.0.0.6; 23.99.204.100;        	|   	|
| Web2    	| No                  	| 40.87.91.168; 10.0.0.5 ; 23.99.204.100        	|   	|
| Elk VM  	| Yes                 	| 40.87.91.168; 10.0.0.5 ;10.0.0.6; 32.213.7.21 	|   	|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because ansible is an open source automation tool. You are able to orchestrate the entire application environment no matter where it is deployed. It is also agentless. All you need to do is to create a SSH key to start managing the system. You then need to write out all the IP addresses of the hosts and write the ansible playbook to install it on all the hosts. You will then run the playbook from your control server/machine. 

The playbook implements the following tasks:
-  In 3-5 bullets, explain the steps of the ELK installation play. E.
- Yml can store content.
- YML can store information about Network connections each time a user tries to connect to the database.
- declare configurations.
- Orchestrate steps pf any manual ordered process on multiple sets of machines in a defined order.
- 

- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Webservers- Web1 and Web2

We have installed the following Beats on these machines:
- Filebeat is configured on Web1 and Web2

These Beats allow us to collect the following information from each machine:
- Filebeat allows to collect data

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the configuration file to /etc/ansible files directory.
- Update the configuration file to include the hosts 
- Run the playbook, and navigate to docker to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- The playbook is in /etc/ansible/roles
- You would update the configuration file t relect the sepcific hosts and associated IP Adresses. In the Playbook - you would write out the the specific hosts the playbook will run. For deploying Filebeat playbook on elk- you would update the filebeat configuraton file to relect ELK and its respective IP address and accessible ports. You would then specify in the playbook to run the script on the ELK Host.  
- You will navigate to the HTTP.://23.99.204.100 - in order to check that the ELK server is running.

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

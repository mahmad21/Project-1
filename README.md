# Project-1
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

root@a393f44d5ddf:/etc/ansible# ls
ansible.cfg  elk.yml  filebeat-config.yml  filebeat.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
The Jump Box serves as the access to the virtual network. This allows the ability to have remote access 
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?
 Deployed in order to monitor all the system logs that are being generated

- _TODO: What does Metricbeat record?_
Metricbeat records uptime and system metrics based around the VMs performance

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Elk     | Elk Server    |   10.1.0.4    |   Linux      |
| Web 1     | Primary Web Access     | 10.0.0.5         | Linux      |
| Web 2 |Backup Web Access    | 10.0.0.6          | Linux           |

### Access Policies
Only the ELK server can accept connections from the Internet
The machines on the internal network are not exposed to the public Internet. 

Only the _____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_ 
13.64.97.109

A summary of the access policies in place can be found in the table below.
Machines within the network can only be accessed by using SSH
Jump Box has access to Elk Server using IP 13.64.97.109

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|      Web 1    |           |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
Quickly deploy a Virtual network 
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
Install docker.io
Install python-pip
Install docker module pip
Increase virtual memory
Downlaod and launch a docker elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
10.0.0.6
We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
DVWA-VM1: Filebeat
These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:

Copy yaml file to the host VM.
Update yaml file to include specified IP and Ports
Run the playbook and navigate to host VM to check the installation worked as expected.
Answer the following questions to fill in the blanks:

Which file is the playbook? The yaml (.yml) file is the playbook which will be running.
Which file do you update to make Ansible run the playbook on a specific machine? 
You the hosts file.
How do I specify which machine to install the ELK server on versus which to install Filebeat on? In the heading of the yaml file next to host, specifify which machine you want to perform the install using the category you listed the machine on in the hosts file.
Which URL do you navigate to in order to check that the ELK server is running? http://52.188.171.241:5601/1

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

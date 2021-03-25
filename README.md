# BenjaminSpidle_Project1_Cybersecuritybootcamp
Project 1 ELK stack for cybersecurity bootcamp UCSD
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/NetworkWatcher_Topology_cybersecuritybootcamp.PNG 
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YML file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._
project1.yml
This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly dynamic, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
Load balancers halt unwanted traffic from entering the main application, an example being URL filtering. Load balancers protect against unwanted injection threats. The advantage of a jump box is that it is used as a security layer in front of other VMs, and that you can primarily monitor the jump box.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the config and system files
- _TODO: What does Filebeat watch for?_specified log files
- _TODO: What does Metricbeat record?_statistics from the operating system

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1      Web Server   10.0.0.5   Linux           
| Web-2      Web Server   10.0.0.6   Linux
| Project1   Web Server   10.1.0.4   Linux        

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jump box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_  76.170.255.196


Machines within the network can only be accessed by the jump box provisioner.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_Jump-box-Provisioner 23.101.198.49

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
| Web-1      No                    76.170.255.196
| Web-2      No                    76.170.255.196
  Project1   Yes/No                76.170.255.196
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_Automating roles to configure and install files

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
Jump-Box-Provisioner 10.0.0.4
Web-1 10.0.0.5
Web-2 10.0.0.6
Project1 10.1.0.4


We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
I installed firebeat. I did not install metricbeat because it said bonus, so I did not think we had to do it.

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Firebeat monitors log files, log events, and locations that are specified by the user, an example being harvesters. Metricbeat monitors for altered data, an example being statistical data. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ansible.cfg file to project1.yml.
- Update the /etc/ansible/host file to include packages we want to install
- Run the playbook, and navigate to Jump-Box-Provisioner to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
ansible.cfg was copied to project1.yml
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
I updated project1.yml, and to specify, I used the internal IP addresses
- _Which URL do you navigate to in order to check that the ELK server is running?
http://20.55.48.87:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

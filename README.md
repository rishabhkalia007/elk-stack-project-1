# elk-stack-project-1
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![CloudHW (4)](https://user-images.githubusercontent.com/36925297/162855142-ad7c9273-72f6-4c62-ab0b-00576afb19bb.jpg)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ReadMe.md file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook filebeat-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly efficient and well managed, in addition to restricting access to the network.
- _TODO: What aspect of security do load balancers protect?
•	Load balancer protects system from DDos attack by splitting traffic.
•	It provides availability aspect of CIA triad.



 What is the advantage of a jump box?_
•	It provides an access from a single node workstation and will be used a secured workstation.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs and system traffic.
- _TODO: What does Filebeat watch for?_
•	Filebeat watches log files and their following location and collect log data. 
•	It monitors the system for any change in the file manager system and logs it.

- _TODO: What does Metricbeat record?_
•	Metricbeat records metric and statistical data from the operating system and from services running on the server.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway | 10.2.0.4   |Linux(ubunto 18.04)|
| Web-1     | Gateway|10.2.0.7    |Linux(ubunto 18.04)|
| Web-2     | Gateway|10.2.0.9    |Linux(ubunto 18.04)|
| ProjectVM| Gateway| 10.3.0.4    |Linux(ubunto 18.04)|

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_
 Ip Address changes every time e.g- 174.93.61.133

Machines within the network can only be accessed by SSH.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
•	174.93.61.135
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  |  |
| Web-1    | No                  |                      |
| Web-2    | No                  |                      |
| ProjectVM| No                  |                      |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
•	All the containers can be configured at once instead of manually editing individual container.
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- INSTALL DOCKER.IO
- INSTALL PYTHON.PIP
- INSTALL DOCKER CONTAINER 
- LAUNCH DOCKER CONTAINER
- INCRESING THE MAP_COUNT

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: ![Docker_project](https://user-images.githubusercontent.com/36925297/162859651-052a73ee-a8b6-4172-b5bb-222d0ea47eda.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
•	Web-1 10.2.0.7
•	Web-2 10.2.0.9

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
•	Filebeat 
•	Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
•	Filebeat- watches log files and their following location and collect log data.
•	Metricbeat- records metric and statistical data from the operating system and from services running on the server.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to etc.ansible.
- Update the config file to include ip addressees of the VMs
- Run the playbook, and navigate to VMs to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
Etc/asible/file
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
We update Host file.
By typing Elk before the elk VMs ip in host file.
- _Which URL do you navigate to in order to check that the ELK server is running?
http://[your.ELK-VM.External.IP]:5601/app/kibana
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

# Cybersecurity
UPENN cybersecurity bootcamp

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://drive.google.com/file/d/1MJGGPdxZVYnFu1DOBcZQKwMGn0ZrKYPd/view?usp=sharing 

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

 ansible-playbook install-elk.yml

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly availible, in addition to restricting traffic to the network.
What aspect of security do load balancers protect? it protects the availibility of the system. What is the advantage of a jump box? a simpler and safer mode of access to the systems.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_ 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function       | IP Address | Operating System |
|----------|----------      |------------|------------------|
| Jump Box | Gateway        | 10.0.0.4   | Linux            |
| web1     | VM             | 10.0.0.7   | linux            |
| web2     | VM             | 10.0.0.8   | linux            |
| ELK-VM   | ELK            | 10.1.0.4   | linux            |
|redteam-LB| loadbalancer   |            | linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- it can only be accesed via my personal IP

Machines within the network can only be accessed by 
jumpbox via ssh.
 -Which machine did you allow to access your ELK VM? jumpbox via ansible.  What was its IP address?_ 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |  68.82.16.162        |
|  web1    | no                  |  10.0.0.7            |
|  web2    | no                  |  10.0.0.8            |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_  simplicity, putting commands from multiple servers into one simple playbook.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ... 1. sudo apt install dockerio
- ... 2. instal pythonpip
- ... 3. systemctl  w vm.max_map_counts_26114

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
web1 10.0.0.7
web2 10.0.0.8
We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
filebeat and metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
 filebeat collects the changes done.
while metricbeat colllects statistics and metrics.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the .yml file to ansible folder.
- Update the config file to include... the correct ip adress
- Run the playbook, and navigate to kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ filebeat config.yml, in etc/ansible/files
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_ jumpbox
- _Which URL do you navigate to in order to check that the ELK server is running?  68.82.16.162/5106

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._


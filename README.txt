## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Diagrams/ElkFinal.pdf)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the [filebeat-playbook.yml]file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: filebeat-playbook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly reliable, in addition to restricting port 80 traffic to the network.

- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_Load balancers protect against distributed denial-of-service attacks.  The advantage of a jump box is that it can be used to configure and make changes to the other VMs all at once from one machine.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_data about file systems
- _TODO: What does Metricbeat record?_machine metrics

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name      | Function | IP Address | Operating System |
|-----------|----------|------------|------------------|
| Jump Box  | Gateway  | 10.0.0.4   | Linux            |
| Web-1     | Server   | 10.0.0.5   | Linux            |
| Web-2     | Server   | 10.0.0.6   | Linux            |
| Web-3     | Logs     | 10.0.0.8   | Linux            |
| ELK-Server| Server   | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the ELK-SERVER machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_69.180.152.238

Machines within the network can only be accessed by JumpBox.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_JumpBox 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|-------------------|------------|----------------------|
| JumpBox           | No         | 69.180.152.238       |
| Web-1             | No         | 40.114.118.138       |
| Web-2             | No         | 40.114.118.138       |
| Web-3             | No         | 40.114.118.138       |
| LoadBalancerWeb123| Yes        | Any                  |
| ELK-SERVER        | No         | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible? The containers are easy to manage.  They can be destroyed and rebuilt very easily.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install Docker.io
- Install pip3
- Install Docker module
- Increase memory
- Download and launch container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Photos/docker_ps_output.pdf)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
-10.0.0.5
-10.0.0.6
-10.0.0.8

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
-filebeat
-metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
- _TODO: What does Filebeat watch for?_data about file systems
- _TODO: What does Metricbeat record?_machine metrics

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_

- _Which file is the playbook? Where do you copy it?_

- _Which file do you update to make Ansible run the playbook on a specific machine? Hosts

-How do I specify which machine to install the ELK server on versus which to install Filebeat on? You can specify which hosts you want to run the playbook on; you’ll want to make sure the correct IPs are under the correct hosts in the hosts file.

- _Which URL do you navigate to in order to check that the ELK server is running? http://104.40.3.131:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
# Project-Elk-Stack
Created an Elk-Stack server in order to set up a cloud monitoring system which details the cloud, network security, and logging and monitoring.

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](C:\Users\mahle\Downloads\README\README\images\Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the YAML files may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._ C:\Users\mahle\Documents\Ansible\install-elk.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting inbound access to the network.
- What aspect of security do load balancers protect?
  - The main purpose of a load balancer is to distribute web traffic across multiple servers so that  this traffic doesn't become bogged down keeping all servers available. A load balancer can help to prevent a Distributed denial of service attack (Ddos) because of the above mentioned.
         
- What is the advantage of a jump box?
  - A jump box also known as a jump server is a gateway on a network that accesses and manages devices in different security zones. In this instance our jump box is the only way that we can access our virtual network via ssh. This limits the ways in which an attacker could access our network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system logs.

- What does Filebeat watch for?
  - Filebeat monitors the log files or locations that are specified. It collects log events, and forwards these to either Elasticsearch or Logstash for indexing. it is essentially looking for any changes.

- What does Metricbeat record?
  - Metricbeat collects system-wide and per-process CPU and memory statistics and sends that data directly to Elasticsearch.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function   | IP Address              | Operating System |
|----------|------------|-------------------------|------------------|
| Jump Box | Gateway    | 20.213.29.11 / 10.0.0.4 | Linux            |
| Web-1    | Webserver  | 10.0.0.7                | Linux            |
| Web-2    | Webserver  | 10.0.0.8                | Linux            |
| Elk-VM   | Kibana     | 20.213.246.24 / 10.1.0.4| Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Elkstack server machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

- Allow from the Workstation public IP via TCP 5601

Machines within the network can only be accessed by Jump-Box-Provisioner.
- Which machine did you allow to access your ELK VM? What was its IP address?

  - Jump-Box-Provisioner IP Address: 10.0.0.4 ssh port 22
  - Workstation Personal Public IP Address TCP port 5601

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses                    |
|----------|---------------------|-----------------------------------------|
| Jump Box | Yes                 | Workstation Public IP Address port 22   |
| Web-1    | No                  | 10.0.0.4 port 22                        |
| Web-2    | No                  | 10.0.0.4 port 22                        |
| Elk-VM   | yes                 | Workstation Public IP Address port 5601 |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because system installation and updates can be streamlined, and processes become more replicable.

- What is the main advantage of automating configuration with Ansible?
  - If adding machines to the network the configuration can be repeated easily as well as no special coding skills needed to use ansible's playbook.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

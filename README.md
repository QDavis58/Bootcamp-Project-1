# Bootcamp-Project-1
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  -install-elk.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly AVAILABLE, in addition to restricting ACCESS to the network.

- Load balancers add protection to DDos attacks by moving traffic from one server to the next. advantage of a Jumpbox is that you can log into other machines without logging in and out. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the SYSLOGS and system METRICS.
-What does Filebeat watch for? it watches for log events
-What does Metricbeat record? it records statistics for Logstash

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| VM-1     |  VM      | 10.0.0.5   | Linux            |
| VM-2     |  VM      | 10.0.0.6   | Linux            |
| ELK      | Server   | 10.0.0.7   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox, Elk server, and Load Balancer machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:


Machines within the network can only be accessed by jumpbox.

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 		        |
| DVWA-VM1 | No                  |                      |
| DVWA-VM2 | No			 |			|
|ELK Server| yes                 |        0.0.0.0       |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
The main advantage is that Ansible will be able to perform tasks on the server without a person on the keyboard. 

The playbook implements the following tasks:

-1. Create ELK server in Azure
-2. Create the ansible playbook 
-3. Install Docker.io, Python Pip, and Docker

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.6
- 10.0.0.7
- 52.226.131.77

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- Filebeat collects log files. For instance, it collects the log data and log events from the elasticsearch.
- Metricbeat collects gets the stats and metircs for elasticsearch. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Filebeat configuration file to the ELK VM.
- Update the Playbook file to include the metricbeat installation tasks
- Run the playbook, and navigate to Kibana to check that the installation worked as expected.

- _Which file is the playbook? Where do you copy it?_
the file is "filebeat-configuration.yml" you copy it to the DVWA VMs 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_

- _Which URL do you navigate to in order to check that the ELK server is running?
http://{VM public Ip address}5601 - Kibana


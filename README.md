# ansible_guide
Description
This repository contains an Ansible playbook designed to install the Ansible tool and Apache web server on a target EC2 instance.

# Prerequisites

Ansible installed on your local machine.
Python: Ansible requires Python to be installed on the control node. Ensure that Python is installed.
An EC2 instance created in your AWS account.


#  Files

 playbook.yaml: Ansible playbook file responsible for installing Apache on the specified host.
 
inventory.yaml: Ansible inventory file containing the details of the host(s) where the playbook will be executed.

# How to Run
Ensure that Ansible is installed on the control machine.
Update inventory.yaml with the correct IP address, SSH user, and private key information for the target host.
Run the playbook using the following command:

~~~
ansible-playbook -i inventory.yaml playbook.yaml
~~~

# Possible Errors and Solutions
Error: No Hosts Matched

Solution:

Verify the following:
The inventory file (inventory.yaml) contains the correct host details.
Ensure the host pattern in the playbook (hosts: Host) matches the defined host or host group in the inventory.

Error: Ansible Requires UTF-8 Locale Encoding ( Installation of Ansible)

Solution:

Set the locale to use UTF-8. You can fix this by setting the environment variable before running the Ansible playbook:

~~~
export LC_ALL="en_US.UTF-8"
export LC_CTYPE="en_US.UTF-8"
ansible-playbook -i inventory.yaml playbook.yaml
~~~

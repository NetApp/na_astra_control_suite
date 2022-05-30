Clone an application using Astra Control
=====

Pre-requisites
------------

1. Ansible with version 2.9 and above.
`NOTE: The playbooks are validated on RHEL 8 & Ubuntu 20.04 machines`

2. Application to be cloned is already managed by Astra Control.

3. If you are cloning the application out of a backup or snapshot of the primary application, the corresponding backup or snapshot should have been successfully completed.

4. Collect the relevant information about Astra Control instance - Astra Control FQDN, Astra Control Account ID and an API token of the user with sufficient privileges to clone the application. 


Variables 
---------

Refer the vars/clone_vars.yml for information on variables.


Procedure 
--------

1. Clone the repository - `git clone https://github.com/NetApp-Automation/na_astra_control_suite.git`

2. Edit the vars/clone_vars.yml file and fill the variables with the details of Astra Control instance and application clone.

3. Run the playbook with the following command - `ansible-playbook clone_app_playbook.yml`

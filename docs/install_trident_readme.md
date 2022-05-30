Install Astra Trident
=====

Pre-requisites
------------

1. Ansible with version 2.9 and above.
`NOTE: The playbooks are validated on RHEL 8 & Ubuntu 20.04 machines`

2. Kubernetes (v1.19+)/OpenShift platform (v4.6+)/Tanzu Kubernetes Grid (1.4+)/Tanzu Kubernetes Grid Integrated (1.12.2+) installed.

3. The backend storage system with the corresponding required configuration. Visit the documentation [here](https://docs.netapp.com/us-en/trident/trident-use/backends.html) to know more about the backend configuration.

Requirements
-----------

1. A DockerHub account to download Astra Trident images.

2. A kubeconfig file with admin access of the Kubernetes/OpenShift/Tanzu cluster on which Astra Trident is planned to be installed on.


Variables
---------

Refer the vars/install_trident_vars.yml for information on variables.


Procedure
--------

1. Clone the repository - `git clone https://github.com/NetApp-Automation/na_astra_control_suite.git`

2. Edit the vars/install_trident_vars.yml file and fill the variables with the information of cluster kubeconfig, DockerHub credentials, Astra Trident backend configuration and StorageClass definition.

3. The playbook requires root privileges to complete some configuration.

4. Run the playbook with the following command if the user is root or the user has passwordless sudo configured - `ansible-playbook install_trident_playbook.yml`

5. Run the playbook with the following command if the user has password based privileged root access configured and then pass the sudo password - `ansible-playbook install_trident_playbook.yml -K`


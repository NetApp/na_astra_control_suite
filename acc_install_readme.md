Pre-requisites for Astra Control Center Installation
------------

1. Ansible with version 2.9 and above.
`NOTE: The playbooks are validated on RHEL 8 & Ubuntu 20.04 machines`

2. Kubernetes (v1.19+)/OpenShift platform (v4.6+) installed [atleast 3 worker nodes with 8 CPUs, 16GB memory and 50GB storage].

3. NetApp Astra Trident installed on the Kubernetes/OpenShift cluster with appropriate backend and storageclass configured.

4. A loadbalancer configured on the Kubernetes/OpenShift cluster for exposing loadbalancer services.

5. A private registry with read/write access.

Requirements for Astra Control Center Installation
-----------

1. Download the Astra Control Center installer tarball from NetApp Support Site [here](https://mysupport.netapp.com/site/products/all/details/astra-control-center/downloads-tab).

2. A kubeconfig file with admin access of the Kubernetes/OpenShift cluster on which Astra Control Center is planned to be installed on.


Variables for Astra Control Center Installation
---------

Refer the vars/install_acc_vars.yml for information on variables.


Procedure for Astra Control Center Installation
--------

1. Clone the repository - `git clone https://github.com/NetApp-Automation/na_astra_control_suite.git`

2. Edit the vars/install_acc_vars.yml file and fill the variables with the information of Astra Control Center installer, cluster kubeconfig, private registry details and Astra Control Center details.

3. The playbook requires root privileges to complete some configuration.

4. Run the playbook with the following command if the user is root or the user has passwordless sudo configured - `ansible-playbook install_acc_playbook.yml`

5. Run the playbook with the following command if the user has password based privileged root access configured and then pass the sudo password - `ansible-playbook install_acc_playbook.yml -K`
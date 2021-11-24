na_deploy_astra_control_center
=========

This ansible role can be used to install the NetApp Astra Control Center on Kubernetes/OpenShift platform. Astra Control Center is an application-aware data management platform from NetApp for protecting, migrating, cloning or restoring the containerized applications.

License
------

By accessing, downloading, installing or using the content in this repository, you agree the terms of the License laid out in [License](license.txt) file.

Note that there are certain restrictions around producing and/or sharing any derivative works with the content in this repository. Please make sure you read the terms of the [License](license.txt) before using the content. If you do not agree to all of the terms, do not access, download or use the content in this repository.

Pre-requisites
------------

    1. Ansible with version 2.9 and above.
    2. Kubernetes (v1.19+)/OpenShift platform (v4.6+) installed [atleast 3 worker nodes with 8 CPUs, 16GB memory and 50GB storage].
    3. NetApp Astra Trident installed on the Kubernetes/OpenShift cluster with appropriate backend and storageclass configured.
    4. A loadbalancer configured on the Kubernetes/OpenShift cluster for exposing loadbalancer services.
    5. A private registry with read/write access.

Requirements
-----------

    1. Download the Astra Control Center installer tarball from NetApp Support Site [here](https://mysupport.netapp.com/site/products/all/details/astra-control-center/downloads-tab).
    2. A kubeconfig file with admin access of the Kubernetes/OpenShift cluster on which Astra Control Center is planned to be installed on.


Variables
---------

Refer the vars/vars.yml for information on variables.


Procedure
--------

1. Edit the vars/vars.yml file and fill the variables with the information of Astra Control Center installer, cluster kubeconfig, private registry details and Astra Control Center details.

2. The playbook requires root privileges to complete some configuration.

3. Run the playbook with the following command if the user is root or the user has passwordless sudo configured - 
    ansible-playbook playbook.yml

4. Run the playbook with the following command if the user has password based privileged root access configured and then pass the sudo password - 
    ansible-playbook playbook.yml -K


Author Information
------------------

- [Nikhil M Kulkarni](nikhil.kulkarni@netapp.com) - NetApp Solutions Automation Team


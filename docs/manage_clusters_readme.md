Register and Manage cluster(s) via Astra Control Center
=====

This playbook can be used to register and manage multiple Kubernetes/OpenShift/Tanzu clusters via Astra Control Center.

Pre-requisites
------------

1. Ansible with version 2.9 and above.
`NOTE: The playbooks are validated on RHEL 8 & Ubuntu 20.04 machines`

2. Kubernetes (v1.19+)/OpenShift platform (v4.6+)/Tanzu Kubernetes Grid (1.4+)/Tanzu Kubernetes Grid Integrated (1.12.2+) installed.

3. For a cluster to be managed by Astra Control Center, it requires Astra Trident to be installed and configured with a backend, a StorageClass be configured with that backend and a snapshot controller with the associated CRDs be deployed. However, it these configurations do not exist on the cluster, you can configure or install them using the same playbook that we use to manage the cluster via Astra Control Center.

Requirements
-----------

1. A DockerHub account to download Astra Trident images, if Astra Trident is to be installed.

2. A kubeconfig file with admin access of the Kubernetes/OpenShift/Tanzu cluster that is being registered and managed by Astra Control Center.


Variables
---------

Refer the vars/manage_clusters_vars.yml for information on variables.


Procedure
--------

1. Clone the repository - `git clone https://github.com/NetApp-Automation/na_astra_control_suite.git`

2. Edit the vars/manage_clusters_vars.yml file and fill the variables with the details of Astra Control instance, cluster kubeconfig files, Astra Trident configuration, and StorageClass definition, if required.

3. Run the playbook with the following command - `ansible-playbook manage_clusters_playbook.yml`


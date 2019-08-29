# Ansible script to setup kubernetes cluster

Kubernetes (K8s) is an open-source system for automating deployment, scaling, and management of containerized applications. 



Kubernetes Master Node: The Kubernetes master is responsible for maintaining the desired state for Kubernetes cluster. 

Kubernetes Worker Node: The nodes in a cluster are the machines (VMs, physical servers, etc) that run the applications and cloud workflows. 
The Kubernetes master controls each worker node.

To Learn more about Kubernetes: https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/


Ansible is an open-source software provisioning, configuration management, and application-deployment tool. 
It runs on many Unix-like systems, and can configure both Unix-like systems as well as Microsoft Windows.

To Learn more abount anible: https://docs.ansible.com/ansible/latest/index.html


#### Prerequisites

  1. 3 or more server running Ubuntu 18.04 LTS (1 server for Master and 2+ servers for worker nodes) with atleast 2GB RAM and 2 vCPU each. The more RAM and CPU for worker node will help to run more applicatons
  2. Ansible installed in your machine https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
  3. git installed in your machine
  
#### Step 1 

Clone the repository
 
 ``` git clone https://github.com/thiyaguin/Ansible-kubernetes-cluster.git ```
 
#### step 2
 
Update the Ansible-kubernetes-cluster\hosts file with IP addresses of Master and workers nodes
 
#### step 3 

Update the CreateK8SCluster.yml - iprange section with IP CIDR block
 
#### step 4 

Run the play book 
 
 ``` ansible-playbook -i hosts CreateK8SCluster.yml ```
 
 

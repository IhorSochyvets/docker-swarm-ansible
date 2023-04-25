# docker-swarm-ansible
Docker Swarm Cluster provisioning using Ansible and AWS free-tier hosts

Original code: https://github.com/acuto/swarm-vagrant-ansible

#ping - test connectivity
ansible all -m ping -v -i inventory

#configure hosts: install docker and some other packages
ansible-playbook -i inventory cluster.yaml

#Swarm Cluster init and choose master
ansible-playbook -i inventory master.yaml

#Join worker nodes (worke1 and worker2) to the cluster
ansible-playbook -i inventory join.yaml

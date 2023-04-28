# docker-swarm-ansible
Docker Swarm Cluster provisioning using Ansible and AWS free-tier hosts

Original code: https://github.com/acuto/swarm-vagrant-ansible

#ping - test connectivity
ansible all -m ping -v -i inventory.ini

#configure hosts: install docker and some other packages
ansible-playbook -i inventory.ini cluster.yml

#Swarm Cluster init and choose master
ansible-playbook -i inventory.ini master.yml

#Join worker nodes (worke1 and worker2) to the cluster
ansible-playbook -i inventory.ini join.yml

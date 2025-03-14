# Ansible

Create 3 AWS VM -> Host Server, Client Server 1, Client Server 2
In Host Server, cd .ssh, generate key **ssh-keygen -t ed25519**  copy key from id_ed25519.pub and  paste it to authorized keys in Client Servers.
In Host Server, to connect to Clients, **ssh ec2-user@Public IPv4 DNS**.

Note: In Linux VM, python is already installed. For Windows VM, python has to be installed.

In Host Server, install ansible **sudo yum install ansible**
ansible --version
copy the IP/fqdn of client servers to inventory file
**cd /etc/ansible**
**sudo vim host** -> Paste Ip of clients here and save by wq!

**ansible all -m ping**  if problem comes check manually ssh@IP

In Client Servers, ssh should be installed, and the service should be started.
**sudo yum install openssh**
**sudo systemctl status sshd**
**sudo systemctl start sshd**

The firewall should be disabled
**sudo systemctl status firewalld**
**sudo systemctl stop firewalld**


## Hosts file can be of two types - ini and yaml
#To create inventory in other that hosts file
**mkdir inv**
**cd inv/**
 1. inventory-ini.yaml
 write Ip in yaml file

**ansible all -i xyz.yaml -m ping**
**ansible webservers -i xyz.yaml -m ping -vvv**

-i to tell that we are replacing the default yaml file
-vvv for detailed debugging

2. inv-yaml.yaml -> inventory-yaml.yaml
   Note: ":" at the end of each line

**Syntax Check**
   ansible-playbook -i inv/inventory-yaml.yaml --syntax-check handlers.yaml 


# Ansible

Create 3 AWS VM -> Host Server, Client Server 1, Client Server 2
In Host Server, cd .ssh, generate key ""ssh-keygen -t ed25519""  copy key from id_ed25519.pub and  paste it to authorized keys in Client Servers.
In Host Server, to connect to Clients, """ssh ec2-user@Public IPv4 DNS"".

Note: In Linux VM, python is already installed. For Windows VM, python has to be installed.

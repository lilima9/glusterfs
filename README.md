# glusterfs
Setup of glusterfs server with Ansible

1. Setup 2 servers using virtualbox.
2. Install openssh-server on 2 servers. Ssh once into the servers before proceeding to add it in the list of known hosts.
2. Install ansible on client. 
3. Add in /etc/hosts of client
  10.131.125.2 server1
  10.131.125.4 server2
4. Ansible uses an inventory file (basically, a list of servers) to communicate with your servers. Like a hosts file (at /etc/hosts) that matches IP addresses to domain names, an Ansible inventory file matches servers (IP addresses or domain names) to groups. Inventory files can do a lot more, but for now, we’ll just create a simple file with one server. Create a file at /etc/ansible/hosts (the default location for Ansible’s inventory file), and add one server to it:
					
   $ sudo mkdir /etc/ansible
   $ sudo touch /etc/ansible/hosts

5. Edit /etc/ansible/hosts
  [web]
  server1
  server2
 
6. Try ping from ansible
  sudo ansible web -m ping -u vagrant --ask-pass

  Should give success
			

 -> Create yml files(playbooks):
 Playbook.yml - glusterfs initial setup
 Glus.yml:starting server and peer probing. Include var file computer_server.yml
 Computeserver.yml: list of servers and thier ip address
 Glus1.yml: volume creation
 computeserver.yml: has the ip addresses of the servers

 Run the playbooks

 Ansible playbook <abc.yml> -u vagrant --ask-pass 

 Should give success

# Ansible

Ansible playbooks to create and manage users on linux systems for security purposes. These playbooks are intended for security analysts and learning purposes, but feel free to fork and modify. There are also sample playbooks I created using Digital Ocean's [Ansible tutorial](https://www.digitalocean.com/community/tutorial_series/how-to-write-ansible-playbooks).

**Please be sure to change password, as these users are created with a default password!**

- install_packages.yaml will install packages based on the debian and red hat systems
- install_nginx.yaml will install the nginx tool
- create_user.yaml file creates users, creates an SSH directory is one doesn't already exists, copies public keys from control node, enables public key authentication and adds users to sudoders file
- users.yaml contains a file of users

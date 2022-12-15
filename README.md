# Ansible

Ansible playbooks to create and manage users on linux systems for security purposes.

- install_packages.yaml will install packages based on the debian and red hat systems
- install_nginx.yaml will install the nginx tool
- create_user.yaml file creates users, creates an SSH directory is one doesn't already exists, copies public keys from control node, enables public key authentication and adds users to sudoders file

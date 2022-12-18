# A List of Helpful Anisble Commands & Resources
------------------------------------------------

### Common Patterns Table

| Pattern | Results |
| ----------- | ----------- |
| all | all hosts from your inventory file |
| host1 | a single (host1) |
| host1:host2 | both host1 and host2 |
| group1:group2 | all servers in group1 and group2 |
| group1:\&group2 | only servers in both group1 and group2 |
| group1:\!group2 | servers in group1 except those also in group2 |


### List machines in your inventory file

``` JavaScript
ansible-inventory -i inventory --list
```

### Execute commands and playbooks with custom inventories
*This command is also used to test connections to ansible hosts*
``` JavaScript
ansible all -i inventory -m ping
```
```
ansible-playbook -i inventory playbook.yml
```

### Target servers in database production groups

``` JavaScript
ansible dbservers:\&production -m ping
```

### Target servers in db but not prod

``` JavaScript
ansible dbservers:\!production -m ping
```

## Manage Multiple Servers with Ad Hoc Commands

### Connect as different remote user

By default, Ansible will connect to the nodes as a remote user with the same name as your current system user 
using its corresponding SSH keypair

``` JavaScript
ansible all -i inventory -m ping -u sammy
```

### Use a custom SSH key to connect

``` JavaScript
ansible all -i inventory -m ping --private-key=~/.ssh/custom_id
```

### Defining Targets for Exection

``` JavaScript
ansible servers -i inventory -m ping
```

``` JavaScript
ansible server1:server2:dbservers -i inventory -m ping
```

``` JavaScript
ansible group1:\!server2 -i inventory -m ping
```

``` JavaScript
ansible group1:\&group2 -i inventory -m ping
```

### Running Ansible Modules

**syntax:** ansible target -i inventory -m module -a "module options"

### The below will use the apt module to install the package tree on server1:
``` JavaScript
ansible server1 -i inventory -m apt -a "name=tree"
```

### Running Bash Commands

``` JavaScript
ansible all -i inventory -a "uptime"
```

### Using Priv Esc to Run Commands with *sudo*

If the command or module you want to execute on remote hosts requires extended system privileges or a different system user, you’ll need to use Ansible’s privilege escalation module, become. This module is an abstraction for sudo as well as other privilege escalation software supported by Ansible on different operating systems.

For instance, if you wanted to run a tail command to output the latest log messages from Nginx’s error log on a server named server1 from inventory, you would need to include the --become option as follows:

``` JavaScript
ansible server1 -i inventory -a "tail /var/log/nginx/error.log" --become
```

Privilege escalation systems such as sudo often require that you confirm your credentials by prompting you to provide your user’s password. That would cause Ansible to fail a command or playbook execution. You can then use the --ask-become-pass or -K option to make Ansible prompt you for that sudo password:

``` JavaScript
ansible server1 -i inventory -a "tail /var/log/nginx/error.log" --become -K
```

## Installing and Removing Packages

The below example uses the apt module to install nginx package on all nodes from inventory file

``` JavaScript
ansible all -i inventory -m apt -a "name=nginx" --become -K
```

Use the *state* arugment set to absent to remove a package
``` JavaScript
ansible all -i inventory -m apt -a "name=nginx state=absent" --become  -K
```

## Copying Files

This is bidirectional - from control node to remote note
``` JavaScript
ansible all -i inventory -m copy -a "src=./file.txt dest=~/myfile.txt"
```

This is from the control node to the control node

``` JavaScript
ansible all -i inventory -m copy -a "src=~/myfile.txt remote_src=yes dest=./file.txt"
```

## Changing File Permissions

``` JavaScript
ansible all -i inventory -m file -a "dest=/var/www/file.txt mode=600 owner=sammy group=sammy" --become  -K
```

## Restarting Services

``` JavaScript
ansible webservers -i inventory -m service -a "name=nginx state=restarted" --become  -K
```

## Restarting Servers

``` JavaScript
ansible webservers -i inventory -a "/sbin/reboot"  --become  -K
```

## Collect Remote Node(s) Info

Obtain system facts on server1:
``` JavaScript
ansible server1 -i inventory -m setup
```

Print only the most relevant information, include the *gather_subet=min* argument:

``` JavaScript
ansible server1 -i inventory -m setup -a "gather_subset=min"
```

Print only specific items, use the *filter* argument

``` JavaScript
ansible server1 -i inventory -m setup -a "filter=*ipv*"
```

Verify disk usage

``` JavaScript
ansible all -i inventory -a "df -h"
```

# Execute Playbooks to Automate Server Setup

## Listing Playbook Tasks

``` JavaScript
ansible-playbook -i inventory playbook.yml --list-tasks
```

## Listing Playbook Tags

``` JavaScript
ansible-playbook -i inventory playbook.yml --list-tags
```

## Executing Tasks by Tag

``` JavaScript
ansible-playbook -i inventory playbook.yml --tags=setup
```

## Skipping Tasks by Tag

``` JavaScript
ansible-playbook -i inventory playbook.yml --exclude-tags=setup
```

## Starting Execution at Specific Task

``` JavaScript
ansible-playbook -i inventory playbook.yml --start-at-task=Copy index page
```

## Limiting Targets for Execution

``` JavaScript
ansible-playbook -l dev -i inventory playbook.yml
```

## Controlling Output Verbosity

Options: -vv or -vvv. Use -vvvv to get connection debugging information
``` JavaScript
ansible-playbook -i inventory playbook.yml -v
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### 

``` JavaScript
```

### I have here: 
- notes for installation and usage of tower-cli on Kali Linux, talking to server with AWX on top of Ubuntu 18.04 LTS.


#############################
#    Jobs for Kimsufi       #
#############################
- IP of server is in hosts to avoid publishing it
- simple administration and management playbooks will be living here



#############################
#     Raspi and Arduino     #
#############################
- IoT and microcomputing will goes here


#############################
#        Projects           #
#############################
- Listing Projects I keep in my home AWX



#############################
#    Ansible Tower CLI      #
#############################
- Installation: pip install ansible-tower-cli

# Instructions:
https://www.unixarena.com/2019/03/ansible-tower-awx-installing-configuring-tower-cli.html/

# Check tower version:
tower-cli --version
Tower CLI 3.3.3

# Usage:
 tower-cli --help Usage: tower-cli [OPTIONS] COMMAND [ARGS]...

Options:
  --version  Display tower-cli version.
  --help     Show this message and exit.

Commands:
  config
  empty
  login
  logout
  receive
  send
  version

Resources:
  activity_stream
  ad_hoc
  application
  credential
  credential_type
  group
  host
  instance
  instance_group
  inventory
  inventory_script
  inventory_source
  inventory_update
  job
  job_template
  label
  node
  notification_template
  organization
  project
  project_update
  role
  schedule
  setting
  team
  user
  workflow
  workflow_job
#

# Show configuration:
 tower-cli config	## Show current config 



# Change configuration:
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$  tower-cli config host https://prg2corp
Configuration updated successfully.
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$  tower-cli config username admin
Configuration updated successfully.
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$  tower-cli config password password
Configuration updated successfully.
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$  tower-cli config

# User options (set with `tower-cli config`; stored in ~/.tower_cli.cfg).
host: https://prg2corp
username: admin
password: password

# Defaults.
use_token: False
verbose: False
certificate: 
format: human
color: True
insecure: False
description_on: False
verify_ssl: True
oauth_token: 


# Customisation:
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$ tower-cli config host http://192.168.0.197
Configuration updated successfully.
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$ tower-cli config

# User options (set with `tower-cli config`; stored in ~/.tower_cli.cfg).
host: http://192.168.0.197
username: admin
password: password
verify_ssl: False

# Queries:
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$ tower-cli organization list
== ======== 
id   name   
== ======== 
 3 blackhat
 2 darknet
 1 Default
== ======== 
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$ tower-cli user list
== ======== ==================== ========== ========= ============ ================= 
id username        email         first_name last_name is_superuser is_system_auditor 
== ======== ==================== ========== ========= ============ ================= 
 1 admin    root@localhost                                    true             false
 5 badlucy  badlucy@darknet.org  badlucy    badlucy          false             false
 4 biglilly biglilly@darknet.org biglilly   biglilly         false              true
 2 jerck    jerk@darknet.org     jerk       jerk one          true             false
 3 luckyboy luckyboy@darknet.org luckyboy   lucky            false             false
== ======== ==================== ========== ========= ============ ================= 
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$ tower-cli role list
== ======= ================= ============= 
id  type     resource_name   resource_type 
== ======= ================= ============= 
30 Admin   Demo Job Template job_template
31 Execute Demo Job Template job_template
32 Read    Demo Job Template job_template
18 Read    Demo Project      project
17 Update  Demo Project      project
15 Admin   Demo Project      project
16 Use     Demo Project      project
21 Read    Demo Credential   credential
20 Use     Demo Credential   credential
19 Admin   Demo Credential   credential
22 Admin   Ansible Galaxy    credential
23 Use     Ansible Galaxy    credential
24 Read    Ansible Galaxy    credential
70 Use     devops-darknet    credential
71 Read    devops-darknet    credential
69 Admin   devops-darknet    credential
73 Use     devops-blackhat   credential
72 Admin   devops-blackhat   credential
74 Read    devops-blackhat   credential
25 Admin   Demo Inventory    inventory
29 Read    Demo Inventory    inventory
27 Ad Hoc  Demo Inventory    inventory
26 Update  Demo Inventory    inventory
28 Use     Demo Inventory    inventory
75 Admin   kimsufi           inventory
== ======= ================= ============= (Page 1 of 4.)
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$ tower-cli job_template list
== ================= ========= ======= =============== 
id       name        inventory project    playbook     
== ================= ========= ======= =============== 
 7 Demo Job Template         1       6 hello_world.yml
== ================= ========= ======= =============== 
cubic@kali450:~/Dropbox/scripts/devops/ansible/tower-cli$ 



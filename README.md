# nagiosxi
This is a ansible playbook to do the below things.

1. Install NRPE on remote Linux server.
ansible-playbook -i inventory/hosts playbooks/nrpe.yml  --vault-password-file password.txt

2. Adding Host to NagiosXI.
ansible-playbook -i inventory/hosts playbooks/add_hosts.yml  --vault-password-file password.txt

3. Adding Service to NagiosXI.
ansible-playbook -i inventory/hosts playbooks/add_service.yml  --vault-password-file password.txt


Change the variabled inside this file accroding to enviornment.
playbooks/group_vars/nrpe_host
---
nrpeurl:  https://assets.nagios.com/downloads/nagiosxi/agents/linux-nrpe-agent.tar.gz
download_dir:  /tmp
nrpesrc:  linux-nrpe-agent
nagiosxi_ip: 192.168.0.130
PROCESS: xinetd
...

This api secret is encrypt using ansible vault

vars/mysecrets.yml
---
apiurl: dsabdksdlsalsadlsadla123213
...

For encrpt:
ansible-vault encrypt vars/mysecrets.yml

For decrypt:
ansible-vault decrypt vars/mysecrets.yml

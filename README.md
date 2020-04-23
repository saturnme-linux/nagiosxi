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
<p>---</p>
<p>nrpeurl: &nbsp;https://assets.nagios.com/downloads/nagiosxi/agents/linux-nrpe-agent.tar.gz</p>
<p>download_dir: &nbsp;/tmp</p>
<p>nrpesrc: &nbsp;linux-nrpe-agent</p>
<p>nagiosxi_ip: 192.168.0.130</p>
<p>PROCESS: xinetd</p>
<p>...</p>

This api secret is encrypt using ansible vault

vars/mysecrets.yml
---
<p>---</p>
<p>apiurl: dsabdksdlsalsadlsadla123213</p>
<p>...</p>
<p><br></p>
<p>For encrpt:</p>
<p>ansible-vault encrypt vars/mysecrets.yml</p>
<p><br></p>
<p>For decrypt:</p>
<p>ansible-vault decrypt vars/mysecrets.yml</p>
<p><br></p>

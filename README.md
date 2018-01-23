*This project is still not usable. Under Development*
But feel free to contribute to it.

#Kubernetes Ansible Playbook (ARM64 + IPv6 only)

*Motivation:* I wanted to setup a kubernetes cluster on ARM64 nodes with IPv6 only. Since this is, I think, the future.
No costs for ip-addresses anymore + cheap and energy efficient cores. But there are issues: Current kubernetes cluster
setup solutions doesn't support this setup. So I do one by myself.

##Preconditions

*Host machine:*
ansible >= 2.4

*Nodes:*
debian | ubuntu (tested on debian 9 so far)


Step 1. Change the certificate configurations
There are a few configurations for the certificate configuration in the folder roles/certificates/templates.
Change the country (C), locality (L), state (ST) in each file. You can also change the size of the key and the other
attributes. But this is only optional.

Step 2. Create a inventory under the root. Name it production, stage or something similar.


Step 3. Run the playbook

ansible-playbook -u root -i production playbook.yaml
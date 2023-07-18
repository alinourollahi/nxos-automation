# nxos-automation
This repository contains ansible scripts for automating repetitive tasks on Cisco Nexus switches.


---

## role: CreateSVI
This ansible role is used for creating SVIs and also configuring HSRP on Nexus switches.
Each time that you run this script, it's going to create an SVI on each of them and also configure HSRP on both of them.

### Inventory
In the inventory directory, there's a file name 'switches' that contains the IP addresses of your switches.
On 'inventory/group_vars', you should provide the SSH information, and on the 'inventory/host_vars' you should specify which switch should be configured as HSRP_1 and which one should be HSRP_2.

### vars
You have to provide the values for these parameters:
   - vlan.id
   - vlan.name
   - vlan.subnet
   - ospf_area

You can also provide the above parameters like this:
ansible-playbook playbooks/add-svi.yml  -e 'vlan.id=VID-100' -e 'vlan.id=100' -e 'vlan.subnet=10.11.12.0/28' -e 'ospf_area=100.100.100.100' -e 'ansible_pasword=1234'


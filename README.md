# nxos-automation

This repository contains Ansible scripts for automating repetitive tasks on Cisco Nexus switches.

---

## Role: CreateSVI

The CreateSVI Ansible role is used for creating SVIs and configuring HSRP on Nexus switches. When running this script, it creates an SVI on each switch and configures HSRP on both switches.

### Inventory

In the `inventory` directory, you'll find the following files:
- `switches`: Contains the IP addresses of your switches.
- `inventory/group_vars`: Specify SSH information.
- `inventory/host_vars`: Specify which switch should be configured as HSRP_1 and which one should be HSRP_2.

### Variables

You need to provide values for the following parameters in 'vars/main.yml' file:
- `vlan.id`
- `vlan.name`
- `vlan.subnet`
- `ospf_area`

Alternatively, you can provide the parameters when running the playbook, like this:
```shell
ansible-playbook playbooks/add-svi.yml -e 'vlan.id=VID-100' -e 'vlan.id=100' -e 'vlan.subnet=10.11.12.0/28' -e 'ospf_area=100.100.100.100' -e 'ansible_password=1234'

```
---

If you have any questions about this repo, feel free to reach me at alinourollahi777@gmail.com.

You can also find me at https://www.linkedin.com/in/ali-nourollahi/.

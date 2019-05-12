**Deploy/remove VMware guests and/or configure dhcpd and named after that.**

**USAGE:**
1) Update group_vars/all file with your VMware configuration
2) Prepare inventory file with exaple listed in hosts file
 
**ROLES:**

deploy_vmware_guests.yml - deploy VMware guests and/or (see tags) update DNS/DHCP configs
remove_vmware_guests.yml - remove VMware guests and/or (see tags) update DNS/DHCP configs

**TAGS:**

_deployvm_ - deploy VMware guest accordinly your inventory hosts files

_removevm_ - remove VMware guest accordinly your inventory hosts files

_dnsupdate_ - only update dns configuration (depends on role)

_dhcpupdate_ - only opdate dhcp condfiguration (depends on role)

_configupdate_ - update dhcp and dns configuration (depends on role)


**EXAMPLES:**

deploy some guests: `ansible-playbook -i hosts deploy_vmware_guests.yml  --diff`

only update dhcp/dns: `ansible-playbook -i hosts deploy_vmware_guests.yml --tags "configupdate" --diff`

remove dhcp/dns but do not remove vmware guests: `ansible-playbook -i hosts remove_vmware_guests.yml --tags "configupdate" --diff`

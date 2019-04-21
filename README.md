Deploy vmware guests and configure dhcpd and named after that.
Usage ansible-playbook -i hosts deploy_vmware_guests.yml --forks=1 --diff 
You need forks=1 to correct update dhcpd configuration while deploying multiple hosts

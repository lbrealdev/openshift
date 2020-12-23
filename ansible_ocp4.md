# Ansible for OpenShift 4


Get data in inventories files and debug:
```
ansible -i /your_inventory/path/*.azure_rm.yaml -m debug -a "msg='Hostname: {{ hostvars[inventory_hostname].name }} IP: {{hostvars[inventory_hostname].ansible_host }}'" all
```

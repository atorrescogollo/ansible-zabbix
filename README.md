Role Name
=========

Zabbix environment manager to easy deploy instances.

- Github repository: https://github.com/atorrescogollo/ansible-zabbix

- Ansible-Galaxy link: https://galaxy.ansible.com/atorrescogollo/ansible_zabbix

Requirements
------------

This role has been tested on Debian 10 machines.

Installation:
```bash
$ ansible-galaxy install atorrescogollo.ansible_zabbix
```

Role Variables
--------------

- `action`: Action to be executed. Posible values:
  - install-server: Zabbix server installation

- `dbname`, `dbuser`, `dbpass`: database name and credentials. Default=zabbix
- `adminpass`: Password for Admin user in Zabbix Frontend. Default=zabbix
- `timezone`: Timezone for PHP. Default=Europe/Madrid

More variables available in defaults/main.yml

NOTE: credentials can be loaded from vars/credentials.yml (i.e. ansible-vault).
NOTE: For autoconfiguration porpuses, zabbix servers and zabbix agents groups must be named
      'zabbix_servers' and 'zabbix_agents', respectively. Alternatively, you can override
      vars 'servers_group_name' and 'agents_group_name' to change group names.

Dependencies
------------

No dependencies

Example Playbook
----------------
```yml
- name: Install Zabbix Server
  hosts: zabbix_servers
  become: yes
  roles:
   - role: atorrescogollo.ansible_zabbix
     vars:
       action: install-server
```

License
-------

MIT

Author Information
------------------
This role was created in 2020 by Álvaro Torres Cogollo.


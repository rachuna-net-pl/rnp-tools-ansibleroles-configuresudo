rnp-tools-ansible-roles-configuresudo
=========

Configuration Sudo roles

![Overwiew](https://gitlab.com/rachuna-net.pl/tools/ansibleroles/rnp-tools-ansibleroles-configuresudo/-/raw/master/docs/configurationSudo.png)

Role Variables
--------------

Defaults role values:
```
input_role_os_distribution: Ubuntu
input_role_custom_groups_to_sudo: []
```

Role vars
```
vars_role_sudo_config_path: /etc/sudoers
```

Example Playbook
--------------

```
    - hosts: servers
      become: yes
      roles:
        - role: rnp-tools-ansible-roles-configuresudo
          vars:
            input_role_os_distribution: "{{ ansible_distribution }}"
            input_role_custom_groups_to_sudo:
              - sysops
              - devops
```

Test Role:
--------------
```bash
# create environment
cd vagrant && vagrant up

# check sudoers file for ubuntu
sudo cat /etc/sudoers |grep %sudo

# check sudoers file for centos
sudo cat /etc/sudoers |grep %wheel

# destroy environment
vagrant destroy
```

License
--------------

BSD 3-Clause

Author Information
--------------

### Maciej Rachuna
SysOps/DevOps
yumrepo Ansible role
====================

Configures yum repositories.

Rationale: This role fits a workflow where group_vars/host_vars is used heavily to specify variables, instead of adding them to individual playbooks. In the latter case, the yumrepo module could be used directly. This role is simply sugar-coating to keep playbooks as small as possible and all data contained in group_vars/host_vars.

Requirements
------------

Ansible >= 2.1

Role Variables
--------------

The role 'supports' (maps, actually) all parameters supported by the [yumrepo](http://docs.ansible.com/ansible/yumrepo_module.html) module.

They should added to the `yumrepo_repositories` variable (list).

Example Playbook
----------------


    - hosts: localhost
      vars:
        yumrepo_repositories:
          - name: CentOS-$releasever - Base
            file: centos-base
            baseurl: http://mirror.netflash.net/centos/$releasever/os/$basearch/
            enabled: yes
            gpgcheck: yes
            gpgkey: file:///etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7

      roles:
        - yumrepo


License
-------

MIT

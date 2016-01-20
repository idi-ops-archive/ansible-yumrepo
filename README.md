yumrepo Ansible role
====================

Configures yum repositories.

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

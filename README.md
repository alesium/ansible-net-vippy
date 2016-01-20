[![Build Status](https://travis-ci.org/alesium/ansible-net-vippy.svg?branch=master)](https://travis-ci.org/alesium/ansible-net-vippy)

net-vippy
=========

Ansible Role to configure vippy from pkgsrc

Requirements
------------

- Hosts requires pkgsrc's pkgin
- Hosts should be bootstrapped for ansible usage (have python,...)
- Root privileges, eg `become: yes`

Role Variables
--------------

| Variable | Description | Default value |
|----------|-------------|---------------|
| `net_vippy_service_name` | Service name for handler | `"pkgsrc/vippy"` | 
| `net_vippy_service_socket_file` | Location of the socket file | `"/var/run/vippy.socket"` | 
| `net_vippy_working_dir` | Working diretory for node | `"net_vippy_working_dir"` | 
| `net_vippy_config_file_src` | vippy.conf.j2 source file location | `"vippy.conf.j2"` | 
| `net_vippy_config_file_dest` | vippy.conf.j2 remote location | `"net_vippy_config_file_dest"` | 
| `net_vippy_node_name` | Node name | `"{{ ansible_hostname }}"` | 
| `net_vippy_node_file` | vippy.node file remote location | `"/opt/local/etc/vippy.node"` | 
| `net_vippy_username` | vippy username | `"root"` | 
| `net_vippy_groupname` | vippy groupname  | `"root"` | 
| `net_vippy_SmartOS_service_bundle_name` | bundle name | `"vippy"` | 
| `net_vippy_SmartOS_service_smf_file` | smf manifest file | `"/opt/local/lib/svc/manifest/vippy.xml"` | 
| `net_vippy_SmartOS_service_svc_file` | smf method file | `"/opt/local/lib/svc/method/vippy-svc"` | 

Dependencies
------------

None

Example Playbook
----------------


    - hosts: servers
      roles:
         - { role: alesium.net-vippy }

License
-------

BSD

Author Information
------------------

Sebastien Perreault <sperreault@alesium.net>

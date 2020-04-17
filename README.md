# Ansible Role: bind
=========

A simple Ansible role for installing and configuring BIND Server for RHEL/CentOS 7.

- Install the necessary packages;
- Create configuration file;
- Create Zones files;


Requirements
------------

- The SELinux and firewall settings are not considered to be a concern of this role.

Attention
---------

DNS knowledge is required to understand the entries and what is being done.

Role Variables
--------------


Variables below are required

| Variable                                     | Default                       | Comments                                     
| :---                                         | :---                          | :---       
|                                              |                               |
| `bind_domain`                                |                               | Inform your domain, example: almircandidodepaula.com 
|                                              |                               |
| `bind_reverse`                               |                               | Inform your reverse IP, example: '0.168.192'
|                                              |                               |
| `bind_reverse_file`                          |                               | Inform your reverse file name, example: '192.168.0'
|                                              |                               |
| `bind_name_servers`                          |                               | Inform your Name Servers, example: ns1.almircandidodepaula.com
|                                              |                               |
| `bind_a_records`                             |                               | Inform A records
|                                              |                               |
| `bind_txt_records`                           |                               | Inform TXT records
|                                              |                               |
| `bind_cname_records`                         |                               | Inform CNAME records
|                                              |                               |
| `bind_mx_records`                            |                               | Inform MX records
|                                              |                               |
| `bind_ptr_records`                           |                               | Inform PTR records
|                                              |                               |
| `bind_master_ip`                             |                               | Inform IP address master server
|                                              |                               |



Dependencies
------------

Example Playbook
----------------

---
- hosts: master,slave
  
  become: yes  

  roles:

    - /path/bind

...


Example inventory file
----------------------
[master]

192.168.0.13

[slave]

192.168.0.9

Instructions
------------
If you are running for the first time creating or creating a new domain, run this way. Do not run twice for the same domain will generate an error in named.local

ansible-playbook playbook_bind.yml

If you are running the second time just to change a record, do it this way.

ansible-playbook playbook_bind.yml --skip-tags "bind_named_local"

## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section.


Author Information
------------------
LinkedIn: https://br.linkedin.com/in/almircandido

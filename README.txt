This is  a simple role for Ansible that configs openVPN for Debian,RedHat,SUSE based Linux. It tested with AWS ubuntu 16.04-18.04, RHEL 10, SUSE 15 
If you found a bug, just write to me plz.
How to work with it? Download it into your ~/roles folder, and create in ansible directory .yml file that contains

--- 
- name: start config OVPN
  hosts: all (you may put your inventory or dynamic inventory file)
  become: yes
  roles:
      -configOVPN
...

RH before name of template means RedHat(template that designed only for RH but also works with SUSE)
After that you may change vars file for your template file
 vars file for configOVPN
ansible_keycount               : UA /*
ansible_keyprov                : OD
ansible_keycity                : OD
ansible_keyorg                 : KZI
ansible_keyemail               : admin@example.com
ansible_keyou                  : Colledge_student */ things for vars.j2&&RHvars.j2  
ovpn_port                      : 443 /*
ovpn_proto                     : tcp   */ things for server.j2 && rhserver.j2
ansible_interface_for_firewall : eth0 // thing for firewall rules, interface that ovpn will use, for default eth0
Enjoy and use it! 




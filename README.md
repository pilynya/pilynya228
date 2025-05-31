# pilynya228
collect_info
---
- name: 
  hosts: info 
  gather_facts: yes 
  tasks: 
    - name:
      copy: 
       dest: /tmp/{{ ansible_hostname }}.yml 
       content: | 
        Hostname: {{ ansible_hostname }} 
        IPAddress: {{ ansible_default_ipv4.address }} 
    - name: 
      fetch: 
	src: /tmp/{{ ansible_hostname }}.yml 
        dest: /etc/ansible/PC-INFO/{{ ansible_hostname }}.yml 
        flat: yes 

![image](https://github.com/user-attachments/assets/96cb4794-f76f-432e-8405-85961f2989bb)

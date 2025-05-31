# pilynya228
collect_info
---
- name: </br>
  hosts: info </br>
  gather_facts: yes </br>
  tasks: </br>
    - name: </br>
      copy: </br>
       dest: /tmp/{{ ansible_hostname }}.yml </br>
       content: | </br>
        Hostname: {{ ansible_hostname }} </br>
        IPAddress: {{ ansible_default_ipv4.address }} </br>
    - name: </br>
      fetch: </br>
	src: /tmp/{{ ansible_hostname }}.yml </br>
        dest: /etc/ansible/PC-INFO/{{ ansible_hostname }}.yml </br>
        flat: yes </br> 

![image](https://github.com/user-attachments/assets/96cb4794-f76f-432e-8405-85961f2989bb)

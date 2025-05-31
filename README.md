# info
collect_info
---
- name: Собираем имя и адрес машин
  hosts: info 
  gather_facts: yes 
  tasks: 
    - name: Создаем файлы с нужными данными
      copy: 
       dest: /tmp/{{ ansible_hostname }}.yml 
       content: | 
        Hostname: {{ ansible_hostname }} 
        IPAddress: {{ ansible_default_ipv4.address }} 
    - name: Перекидываем файлы с удаленного хоста
      fetch: 
	src: /tmp/{{ ansible_hostname }}.yml 
        dest: /etc/ansible/PC-INFO/{{ ansible_hostname }}.yml 
        flat: yes 

![image](https://github.com/user-attachments/assets/96cb4794-f76f-432e-8405-85961f2989bb)

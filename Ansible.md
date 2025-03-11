
# ANSIBLE

1. What is Ansible, and how does it work?
```
Answer: Ansible is a configuration management tool that automates infrastructure tasks using YAML-based Playbooks. It is agentless and uses SSH for communication.
```
2. What is an Ansible Playbook?
```
Answer: An Ansible Playbook is a YAML file containing tasks to automate configurations and deployments.
```
3.What are Ansible Roles?
```
Answer: Roles help in structuring Ansible Playbooks by organizing tasks, handlers, and variables into reusable components.
```
4. How do you execute an Ansible Playbook?
```
Answer:
ansible-playbook playbook.yml
```
5. What is an inventory file in Ansible?
```
Answer: The inventory file defines the list of managed hosts, specifying IPs and groups.
```
6. What is the difference between ad-hoc commands and Playbooks?
```
Answer:
Ad-hoc commands execute single tasks, e.g.,
ansible all -m ping
Playbooks define structured workflows for automation.
```
7. What are handlers in Ansible?
```
Answer: Handlers are triggered by tasks and execute actions like restarting services when there is a change.
```
8. What are variables in Ansible, and how do you use them?
```
Answer: Variables store dynamic values and can be used in Playbooks using {{ variable_name }} syntax.
```
9.How do you use loops in Ansible?
```
Answer:

- name: Install multiple packages
  yum:
    name: "{{ item }}"
    state: present
  loop:
    - httpd
    - mysql
    - php
```
10. How do you secure sensitive information in Ansible?
```
Answer: By using Ansible Vault, e.g.,
ansible-vault encrypt secrets.yml
```
11. Coding Task Write an Ansible Playbook to install Nginx.
```
- hosts: all
  become: yes
  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present

```

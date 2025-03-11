# CICD (GITLAB & JENKINS)
1. What is CI/CD, and why is it important in DevOps?
```Answer:
CI/CD (Continuous Integration and Continuous Deployment/Delivery) automates the process of integrating code changes, testing, and deploying applications. It ensures:
Faster releases
Improved code quality
Reduced manual intervention
```
2. Explain the difference between Continuous Integration, Continuous Delivery, and Continuous Deployment.
```
Answer: Continuous Integration (CI): Developers merge their code frequently into a shared repository, with automated testing.
Continuous Delivery (CD): Builds and tests the code, ensuring it's always ready for deployment. Manual approval is required for production release.
Continuous Deployment: Fully automates the deployment process without manual intervention.
```

3. How do you create a pipeline in Jenkins?
```
Answer:
You can create a pipeline in Jenkins by using a Jenkinsfile, which defines the build, test, and deployment steps using Declarative or Scripted syntax.
```
4. What is a Jenkinsfile?
```
Answer: A Jenkinsfile is a script that defines a CI/CD pipeline in Jenkins using either Declarative or Scripted syntax. It helps in automating the CI/CD workflow.
```
5. What is an agent in Jenkins, and how do you configure it?
```
Answer: An agent (or node) in Jenkins is a machine that runs the pipeline tasks. It can be configured as:
Static Agent: A dedicated machine
Dynamic Agent: Using Docker, Kubernetes, or cloud services
```

6. How does GitLab CI/CD work?
```
Answer: GitLab CI/CD works using a .gitlab-ci.yml file, where you define jobs, stages, and scripts for building, testing, and deploying applications. GitLab Runners execute the pipeline jobs.
```

8. What are GitLab Runners, and how do you configure them?
```
Answer: GitLab Runners are agents that execute CI/CD jobs. You can configure a runner using the command:
gitlab-runner register --url <GITLAB_URL> --registration-token <TOKEN>
```

9. How do you integrate Jenkins with Git repositories?
```
Answer: Jenkins integrates with Git using the Git Plugin. You need to Provide the repository URL in the pipeline configuration
Set up webhook triggers for automated builds
```
9. What is a webhook in GitLab, and how is it used in CI/CD?
```
Answer:
A webhook is a trigger that notifies GitLab CI/CD when changes are pushed, automatically triggering a pipeline.
```
10. How do you manage secrets in Jenkins/GitLab CI/CD?
```
Answer:

In Jenkins: Secrets are stored using Jenkins Credentials
In GitLab: You can use CI/CD Variables or HashiCorp Vault
```

11. Write a simple Jenkins pipeline to build and deploy a Java application.
```
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp target/app.jar user@server:/app'
            }
        }
    }
}
```

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
# SHELL SCRIPTING

1. What is a shell script?
```
Answer: A shell script is a text file containing commands that run in a Unix/Linux shell.
```
2. How do you create and execute a shell script?
```
Answer:
nano script.sh
chmod +x script.sh
./script.sh
```
3. What is the difference between " and ' in shell scripting?
```
Answer: " " allows variable expansion, while ' ' treats everything as a literal string.
```
4. What is the purpose of set -e in shell scripts?
```
Answer: It stops execution if any command fails.
```
5. How do you define and use functions in shell scripting?
```
Answer:
function say_hello() {
    echo "Hello, $1!"
}
say_hello "User"
```
6. Coding Task Write a shell script to check if a given number is even or odd.
```
#!/bin/bash
echo "Enter a number:"
read num
if (( num % 2 == 0 )); then
    echo "Even"
else
    echo "Odd"
fi
```

# PYTHON

1. What is Python, and why is it used in DevOps?
```
Answer: Python is a scripting language used for automation, CI/CD, and cloud management.
```
2. How do you read a file in Python?

Answer:
```
with open('file.txt', 'r') as f:
    content = f.read()
print(content)
```
3. Coding Task
Write a Python script to fetch metadata from an AWS EC2 instance.
```
import requests
response = requests.get('http://169.254.169.254/latest/meta-data/')
print(response.text)
```

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

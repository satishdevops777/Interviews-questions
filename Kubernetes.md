# KUBERNETES


1. What is Kubernetes, and why is it used?
```
Answer: Kubernetes automates the deployment, scaling, and management of containerized applications.
```
2. What are Pods in Kubernetes?
```
Answer: Pods are the smallest deployable units in Kubernetes, containing one or more containers.
```
3.What is a Kubernetes Deployment?
```
Answer: A Deployment manages replicas of Pods and ensures zero-downtime updates.
```
4.What is a Kubernetes Service?
```
Answer: A Service exposes a set of Pods to external traffic.
```
5. How do you check running Pods in Kubernetes?
```
Answer:

kubectl get pods
```
6.What is a ConfigMap in Kubernetes?
```
Answer: ConfigMaps store non-sensitive configuration data for applications.
```
7. What is a Persistent Volume (PV) in Kubernetes?
```
Answer: PVs provide persistent storage for Pods.
```
8. How do you scale a Kubernetes Deployment?
```
Answer:
kubectl scale deployment myapp --replicas=5
```
9. What is the difference between a StatefulSet and a Deployment?
```
Answer:
Deployment: For stateless applications.
StatefulSet: For stateful applications (e.g., databases).
```
10. What is a Helm chart?
```
Answer: A package manager for Kubernetes, automating application deployment.
```
11. Coding Task Write a Kubernetes Deployment YAML for an Nginx Pod.
```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest

```

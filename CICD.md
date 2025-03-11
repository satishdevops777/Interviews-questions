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

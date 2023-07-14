# Terraform CI/CD Pipeline

## **List of Tools used**
- Maven 
- Jenkins
- Docker
- Terraform
- AWS

### How Pipeline works?
- Using Jenkins
`Source code is pulled from git repo` -> `Maven Builds the package` -> `Docker builds a docker image and push it to dockerhub repo` -> `Terraform Provision AWS service including Ec2 instance` -> `Docker Image is installed on EC2 instance`

## Pre-Req
- Jenkins Instance
- SSHagent plugin For Jenkins
- Install Maven,Docker,AWS Cli and Terraform in Jenkins Instance
- Docker,Git and AWS credentials should be added in Jenkins Credentials Manager
- Update Credentials variable in Jenkinsfile
- Update Variables in terraform/variables.tf
- SSH key pair to connect to EC2 instance

## S3 Bucket
`We need to manually create S3 bucket named 'myapp-bucket', to store terraform state remotely`

#### Note
`In Jenkinsfile, provision stage we wait for 90 seconds in that time we wait for aws services to be provisioned and install dependencies, if we don't wait and the instance hasn't been created beforehand, deployment stage will fail`

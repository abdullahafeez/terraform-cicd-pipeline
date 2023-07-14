# terraform-cicd-pipeline

## **List of Tools used**
- Maven 
- Jenkins
- Docker
- Terraform
- AWS

### How Pipeline works?
- Using Jenkins
`Source code is pulled from git repo` -> `Maven Builds the package` -> `Docker builds a docker image and push it to dockerhub repo` -> `Terraform Provision AWS service including Ec2 instance` -> `Docker Image is installed on EC2 instance`


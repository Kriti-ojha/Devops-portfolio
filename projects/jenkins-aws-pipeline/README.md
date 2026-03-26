# Jenkins AWS Pipeline

## Overview
A minimal CI/CD demo that automates checkout, build, test (placeholders), and deployment of a static web page to AWS S3 using Jenkins.

## What You Will Learn
- Installing and configuring Jenkins
- Creating a Jenkins pipeline with a Jenkinsfile
- Integrating Jenkins with GitHub
- Deploying artifacts to AWS S3 using AWS CLI

## Files
- `index.html` — simple static page to deploy
- `Jenkinsfile` — pipeline definition (checkout, build, test, deploy)
- `README.md` — this file

## Prerequisites
- A GitHub repository containing this project
- Jenkins server or EC2 instance with Jenkins installed
- AWS account and an S3 bucket (example: `my-jenkins-demo-bucket`)
- AWS CLI installed and configured on the Jenkins agent or Jenkins running on an EC2 instance with an appropriate IAM role

## Setup Steps

1. Create S3 bucket
   - Create a public or website-enabled S3 bucket for demo purposes.

2. Configure AWS credentials
   - On Jenkins host run `aws configure` or attach an IAM role with `s3:PutObject` permission.

3. Add project to repo
   - Place this folder under `projects/jenkins-aws-pipeline` in your `Devops-portfolio` repo.

4. Create Jenkins pipeline job
   - New Item → Pipeline → Pipeline script from SCM → Git URL: `https://github.com/<your-github-username>/Devops-portfolio.git` → Branch: `main`
   - Save and Build Now.

5. Verify deployment
   - Open `https://<bucket-name>.s3.<region>.amazonaws.com/index.html` or the S3 website endpoint.

## Security Notes
- Do not hardcode AWS keys in the Jenkinsfile.
- Use Jenkins credentials or IAM roles for secure access.

## Future Improvements
- Add unit tests and linting in Test stage
- Deploy to EC2 or use CodeDeploy for more realistic deployments
- Add notifications on pipeline status (Slack or email)

# Automating-CI-CD-with-GitHub-Actions-and-AWS
Hey devs! 👋
In this post, I’ll walk you through how I built a CI/CD Pipeline using GitHub Actions and AWS — a powerful and cost-effective DevOps workflow that automatically deploys code to EC2 or S3 and notifies you via Amazon SNS.

Project Name: CI/CD with GitHub Actions
Tools Used: GitHub Actions, AWS EC2, AWS S3, IAM Roles, SNS
Type: Real-world, Cloud DevOps Project
Infra as Code: Optional for IAM policies

Project Overview
This project demonstrates how to:
Trigger a GitHub Action on every push to the main branch.
Deploy code automatically to an EC2 instance or S3 bucket.
Use secure IAM roles to control access.
Send notifications to your email via Amazon SNS once deployment is successful.

Architecture Diagram
GitHub Repo --> GitHub Actions Workflow --> AWS IAM Role (OIDC Auth) --> EC2/S3 Deployment
                                                               |
                                                               └--> SNS (Email Notification)


CI/CD Workflow Breakdown
1. GitHub Repo Setup
Push your project (e.g., frontend or backend) to a GitHub repository. Create a .github/workflows/deploy.yml file for the pipeline config.
2. Set Up IAM Role with GitHub OIDC
Enable OIDC provider for GitHub in your AWS account.
Create an IAM role with trust policy allowing GitHub to assume it.
Attach necessary policies (EC2 or S3 + SNS).
3. Sample GitHub Actions Workflow

After a successful deployment, you’ll get an email like this:
Subject: CI/CD Pipeline
Message: Deployment to AWS successful!
Security Considerations
Use least privilege IAM policies.

Rotate GitHub secrets regularly if used (e.g., for non-OIDC-based deployments).
Use environment-specific roles if deploying to multiple accounts or stages.

Outcomes
Fully automated zero-touch deployment pipeline.
Learned GitHub-AWS OIDC integration.
Built production-grade notification system using SNS.
Highly reusable across projects (frontend or backend).

For a detailed article, check here: https://nandiniduggineni.hashnode.dev/automating-cicd-with-github-actions-and-aws-project-walkthrough
Conclusion

CI/CD pipelines shouldn't be a bottleneck — this project proves how powerful GitHub + AWS can be for lean DevOps setups. Let me know what you'd add or improve!

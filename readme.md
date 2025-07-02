# AWS ECS Image Uploader with S3

![AWS Architecture Diagram](./assets/architecture-diagram.png) *(Example - replace with your actual diagram)*

A highly available containerized web application deployed on AWS ECS that allows users to upload and view images stored in S3. The infrastructure is provisioned using AWS CloudFormation with VPC endpoints for secure internal communication.

## Features
- **Infrastructure**:
  - Custom VPC with public/private subnets
  - VPC endpoints for S3, ECR, and CloudWatch
  - Application Load Balancer (ALB) for traffic distribution
  - Auto-scaling based on CPU utilization

## Architecture

### Core Components

1. **VPC Network**:
   - Public subnets (ALB)
   - Private subnets (ECS tasks)
   - VPC endpoints for AWS services

2. **Compute**:
   - ECS Fargate cluster
   - Service with auto-scaling (2-4 tasks)

3. **Storage**:
   - S3 bucket for image storage
   - RDS addition
   - CloudWatch for logs

4. **Security**:
   - Security groups restricting traffic
   - IAM roles with least privilege


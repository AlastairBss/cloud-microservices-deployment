
# Project Overview


Infrastructure: Containerized microservices deployed on AWS ECS Fargate with automated CI/CD pipelines and load-balanced traffic management.

## Architecture
This project demonstrates deployment of a containerized multi-service application on AWS using a production-style cloud architecture:
* Frontend & Backend Containers deployed on Amazon ECS Fargate
* Docker images stored in Amazon ECR
* Application Load Balancer (ALB) routes traffic to services
* CI/CD pipeline using GitHub → CodePipeline → CodeBuild
* CloudWatch Logs used for monitoring and debugging
### Architecture highlights:
* Fully containerized deployment
* Automated build and redeployment pipeline
* Load-balanced scalable infrastructure
* Environment variable management for secrets
* Health checks configured for service reliability

## Tech Stack
### Cloud & Infrastructure
* AWS ECS Fargate
* Amazon ECR
* Application Load Balancer (ALB)
* AWS CodePipeline
* AWS CodeBuild
* Amazon CloudWatch
### DevOps & Tools
* ADocker
* AGitHub CI/CD integration
### Backend
* Python (FastAPI / render)
### Frontend
* Streamlit-based UI

## Deployment Flow
The application follows an automated CI/CD deployment pipeline:

* Code pushed to GitHub repository <br/>
                 &darr;
* AWS CodePipeline triggers automatically <br/>
<img src="/home/alastairlinux/brave_screenshot_us-east-1.console.aws.amazon.com (1).png" alt="Alt text" width="300" height="200">

                &darr;
* CodeBuild builds Docker images <br/>
                &darr;

* Images pushed to Amazon ECR <br/>
&darr;
* ECS services updated with new image <br/>
&darr;
* Application redeployed via Fargate behind ALB 

### This enables continuous deployment without manual infrastructure updates.

## Key Learnings
### Cloud Networking

* ECS service networking configuration

* Load balancer routing setup

* Security group debugging

### IAM & Permissions

* Resolving ECR authentication failures

* Managing CodeBuild service roles

* Secure environment variable handling

### Deployment Reliability

* Health check configuration

* Container restart troubleshooting

* CI/CD pipeline debugging

## Local Development Setup
Build Containers for frontend and Backend
> docker build -t backend ./backend <br/>
> docker build -t frontend ./frontend

Run Containers
> docker run -p 8000:8000 backend <br/>
> docker run -p 8501:8501 frontend

## Project Highlights
* End-to-end AWS cloud deployment
* Containerized microservices architecture
* Automated CI/CD pipeline implementation
* Production-style load balancing setup
* Hands-on debugging of real cloud infrastructure

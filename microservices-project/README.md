
# Project Overview
WebAPP (Inbox Intelligence)
* AI-powered email organizer that connects to a Gmail account to simplify inbox management.
* Backend (FastAPI) handles Google OAuth login and securely accesses Gmail data.
* Fetches recent emails and extracts key details like sender, subject, and preview snippet.
* Uses an AI model to classify emails into categories such as action-required, application updates, academic   emails, and promotions/noise.
* Categorized data is temporarily stored and sent to a frontend dashboard.
* Frontend (Streamlit) displays emails in a structured interface with metrics, tabs, search filtering, and *   quick Gmail links.
* Overall purpose is to reduce email clutter and help users quickly identify important messages.
  
Infrastructure: Containerized microservices deployed on AWS ECS Fargate with automated CI/CD pipelines       and load-balanced traffic management.

-----------------------------
## Architecture
This project demonstrates deployment of a containerized multi-service application on AWS using a production-style cloud architecture:
* Frontend & Backend Containers deployed on Amazon ECS Fargate
* Docker images stored in Amazon ECR
* Application Load Balancer (ALB) routes traffic to services
* CI/CD pipeline using GitHub → CodePipeline → CodeBuild
![Alt text](https://github.com/AlastairBss/cloud-microservices-deployment/blob/bad6a33da772383c8b329787f4a5fef62ccc84e2/microservices-project/codebuild.png)
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
* AWS CodePipeline triggers automatically
  <br/>
![Alt text](https://github.com/AlastairBss/cloud-microservices-deployment/blob/1a4d137cee2425b1758ac5f833f9be29231fd528/microservices-project/brave_screenshot_us-east-1.console.aws.amazon.com%20(1).jpg)
               
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

## Architecture Diagram
![Alt text](https://github.com/AlastairBss/cloud-microservices-deployment/blob/85e64eb19ff1ad388f3fe569fcb747fde89e9e05/microservices-project/arc%20(1)%20(1).png)

## Project Highlights
* End-to-end AWS cloud deployment
* Containerized microservices architecture
* Automated CI/CD pipeline implementation
* Production-style load balancing setup
* Hands-on debugging of real cloud infrastructure

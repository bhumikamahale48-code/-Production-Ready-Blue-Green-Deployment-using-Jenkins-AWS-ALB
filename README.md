# Production-Ready Blue-Green Deployment using Jenkins & AWS ALB
Project Overview

This project demonstrates a production-ready Blue-Green Deployment strategy using:

Jenkins CI/CD
AWS EC2
Application Load Balancer (ALB)
Target Groups
Nginx
Automatic Rollback Mechanism

The goal is to achieve zero-downtime deployments with instant rollback capability.

Infrastructure Setup
EC2 Instances Running

Three servers are running:

Jenkins Server
Blue Environment Server
Green Environment Server

# EC2 Running


<img width="850" height="371" alt="image" src="https://github.com/user-attachments/assets/f8300ca5-50ca-474d-ae38-304cfdd169db" />

Target Group Health Status

Both Blue and Green environments remain healthy.

# Blue-TG → Healthy

<img width="849" height="328" alt="image" src="https://github.com/user-attachments/assets/8359c63a-cbca-4c4c-8262-a97a053e47ca" />


# Target Groups Healthy

Green-TG → Healthy

<img width="843" height="366" alt="image" src="https://github.com/user-attachments/assets/4e70aa4a-55aa-4a11-822b-f1ebae8cd93e" />


Target Groups Healthy

This ensures instant rollback capability.

ALB Traffic Routing

# Traffic Forwarded to Green

<img width="842" height="341" alt="image" src="https://github.com/user-attachments/assets/f88eb916-85f8-4f4e-90cd-05073bb9350a" />


ALB Forward Green

Listener → Forward to Green Target Group

 # Traffic Forwarded to Blue

<img width="834" height="363" alt="image" src="https://github.com/user-attachments/assets/e6c0920a-cce5-4bad-af1b-1b834ab41731" />

ALB Forward Green

Listener → Forward to Green Target Group

Application Output

# Blue Environment Output

<img width="771" height="297" alt="image" src="https://github.com/user-attachments/assets/d055c403-01f7-4234-97ab-785ca2ebdbb8" />


Blue Output

Green Environment Output

# Green Output

<img width="798" height="237" alt="image" src="https://github.com/user-attachments/assets/b9c5232a-1008-47b2-8ddd-87ca4627b17f" />


Jenkins Pipeline Execution
Successful Deployment (Healthy)

Green deployment successful
Target group health verified

# Traffic switched to Green

<img width="852" height="441" alt="image" src="https://github.com/user-attachments/assets/f8cad911-e8a2-479d-87d3-0136c0a2e13a" />


Pipeline Success

Automatic Rollback Demonstration

# Green-TG → Unhealthy

<img width="852" height="388" alt="image" src="https://github.com/user-attachments/assets/ab119944-0124-4591-a8c5-55dcf682fadf" />


Target Groups Healthy

If Green fails health check:

Jenkins detects failure
Traffic automatically switches back to Blue
Zero downtime maintained

# Pipeline Failure (Unhealthy Green)

<img width="850" height="425" alt="image" src="https://github.com/user-attachments/assets/9ec1112c-6f79-4c43-b203-02c68f9c7af0" />

Pipeline Failure

# Listener Forwarded Back to Blue

<img width="786" height="250" alt="image" src="https://github.com/user-attachments/assets/ceca8d39-6c29-43aa-8c9f-11464a786506" />

Rollback to Blue Listener → Forward to Blue Target Group

 # Deployment Flow
Code Checkout from GitHub
Deploy to Green Server
Wait for Target Registration
Verify Target Group Health
Switch Traffic to Green
Automatic Rollback on Failure
IAM Permissions Used
Jenkins requires:

elasticloadbalancing:DescribeTargetHealth
elasticloadbalancing:ModifyListener
Key Features
✔ Zero Downtime Deployment
✔ Automated Health Check Validation
✔ Instant Rollback
✔ High Availability
✔ Production-Ready CI/CD Pipeline

# Interview Explanation
In this architecture:

Both Blue and Green environments remain healthy.
Traffic switching is handled at ALB level.
Rollback is automatic if health checks fail.
This ensures high availability and reliability in production systems.
Conclusion
This project successfully demonstrates a real-world DevOps Blue-Green Deployment strategy using Jenkins and AWS infrastructure.

# It guarantees:

Continuous Delivery
Safe Deployments
Instant Rollback
High Reliability

# Author

Bhumika Devsing Mahale














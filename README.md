🚀 Production-Ready Blue-Green Deployment using Jenkins & AWS ALB
📌 Project Overview

This project demonstrates a production-grade Blue-Green Deployment strategy using:

Jenkins CI/CD Pipeline
AWS EC2 Instances
Application Load Balancer (ALB)
Target Groups
Nginx Web Server
Automated Rollback Mechanism

The main objective is to achieve zero-downtime deployments with instant rollback capability.

🏗️ Architecture Diagram (Concept)
        Users
          |
          v
       AWS ALB
      /       \
 Blue-TG     Green-TG
   |             |
 Blue EC2     Green EC2
          |
       Jenkins
⚙️ Infrastructure Setup
🖥️ EC2 Instances

Three EC2 instances are used:

<img width="850" height="371" alt="image" src="https://github.com/user-attachments/assets/35419591-cef7-43a0-87c9-35527099536a" />

Jenkins Server → CI/CD pipeline execution
Blue Environment Server → Stable live environment
Green Environment Server → New deployment environment

❤️ Target Group Health

Both environments stay healthy for safe switching:

✅ Blue Target Group → Healthy

<img width="849" height="328" alt="image" src="https://github.com/user-attachments/assets/947cfbe9-7566-4eef-9260-ec6110114b49" />

✅ Green Target Group → Healthy

<img width="843" height="366" alt="image" src="https://github.com/user-attachments/assets/efca3618-ccc8-49eb-bae0-ac05d0dada5d" />


This ensures:

Instant rollback
High availability
🌐 ALB Traffic Routing
🔹 Before Deployment
ALB → Routes traffic to Blue
🔹 After Successful Deployment
ALB → Switches traffic to Green
🔹 On Failure
ALB → Automatically routes back to Blue
🧪 Application Output
Blue Environment → Old Version
Green Environment → New Version
🔄 Jenkins Pipeline Flow
Checkout Code from GitHub
Deploy to Green Server
Wait for Target Registration
Verify Target Group Health
Switch Traffic to Green
Monitor Deployment
Rollback Automatically (if failure)
✅ Successful Deployment
Green environment becomes healthy
Traffic switches to Green
Deployment completed with zero downtime
❌ Failure Scenario (Automatic Rollback)

If Green fails health checks:

Jenkins detects failure
ALB switches traffic back to Blue
No user impact (zero downtime maintained)
🔐 IAM Permissions Required

Jenkins needs the following AWS permissions:

elasticloadbalancing:DescribeTargetHealth
elasticloadbalancing:ModifyListener
⭐ Key Features

✔ Zero Downtime Deployment
✔ Automated Health Check Validation
✔ Instant Rollback
✔ High Availability
✔ Production-Ready CI/CD Pipeline

🎯 Interview Explanation
Both environments (Blue & Green) remain active
Traffic switching happens at ALB level
Health checks ensure only stable deployments go live
Rollback is automatic and instant

👉 This architecture ensures:

High availability
Reliability
Safe production deployments
📊 Benefits
Continuous Delivery
Risk-Free Releases
Fast Recovery from Failures
Scalable Architecture
🧾 Conclusion

This project successfully demonstrates a real-world DevOps deployment strategy using AWS and Jenkins.

It ensures:

🚀 Continuous Delivery
🔄 Safe Deployments
⚡ Instant Rollback
🛡️ High Reliability
👨‍💻 Author

Riyaj Jamir Kalawant

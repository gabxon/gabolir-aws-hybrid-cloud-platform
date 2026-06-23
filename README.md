# AWS High Availability Hybrid Cloud Platform

## Project Overview

This project demonstrates the design and implementation of a highly available and self-healing web platform on Amazon Web Services (AWS).

The solution leverages Amazon EC2, Application Load Balancer (ALB), Auto Scaling Groups (ASG), Route 53, CloudWatch, and Multi-AZ deployment to ensure fault tolerance, scalability, and high availability.

The project was built and tested by intentionally terminating running EC2 instances and validating that the Auto Scaling Group automatically launched replacement instances while maintaining application availability through the Application Load Balancer.

---

## Architecture Summary

### AWS Services Used

* Amazon EC2
* Application Load Balancer (ALB)
* Auto Scaling Group (ASG)
* Amazon Route 53
* Amazon CloudWatch
* AWS Certificate Manager (ACM)
* Amazon VPC
* Public Subnets

### Infrastructure Components

| Component          | Configuration         |
| ------------------ | --------------------- |
| Region             | us-east-1             |
| VPC                | vpc-076a595462854afed |
| Load Balancer      | gabolir-alb           |
| Target Group       | gabolir-web-tg        |
| Auto Scaling Group | gabolir-asg           |
| Desired Capacity   | 2                     |
| Minimum Capacity   | 2                     |
| Maximum Capacity   | 4                     |
| Security Group     | launch-wizard-2       |
| Web Server         | Apache HTTPD          |

---

## High Availability Design

The platform is deployed across multiple Availability Zones:

* us-east-1a
* us-east-1c

Traffic is distributed through the Application Load Balancer, ensuring continuous service availability even if an EC2 instance fails.

---

## Auto Scaling Demonstration

The Auto Scaling Group was configured with:

* Minimum Capacity: 2
* Desired Capacity: 2
* Maximum Capacity: 4

When an EC2 instance was manually terminated, the Auto Scaling Group automatically launched a replacement instance to maintain the desired capacity.

---

## Self-Healing Infrastructure Test

### Test Performed

1. Verified two healthy EC2 instances.
2. Manually terminated one running instance.
3. Auto Scaling Group detected capacity reduction.
4. New replacement instance launched automatically.
5. Target Group health checks passed.
6. Website remained accessible through the Load Balancer.

### Result

Successful demonstration of AWS self-healing infrastructure and high availability architecture.

---

## Skills Demonstrated

* AWS EC2 Administration
* Application Load Balancer Configuration
* Auto Scaling Group Deployment
* Route 53 Integration
* CloudWatch Monitoring
* High Availability Architecture
* Infrastructure Resilience Testing
* Linux Server Administration
* Apache HTTPD Deployment
* AWS Networking

---

## Screenshots

Screenshots and evidence of deployment, health checks, Auto Scaling activities, and load balancing are available in the `/screenshots` folder.

---

## Author

**Gabriel Tobi Idowu**

CCNA Certified Network Engineer
AWS Solutions Architect Associate (In Progress)

GitHub: https://github.com/gabxon

---

## Project Status

Completed and Operational

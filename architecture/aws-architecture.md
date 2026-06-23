Internet Users
      |
      ▼
CloudFront Distribution
(www.gabolirmultiantionals.com.ng)
      |
      ▼
AWS Certificate Manager (SSL/TLS)
      |
      ▼
Amazon Route 53
      |
      ▼

+----------------------------------+
| VPC: vpc-076a595462854afed       |
| Region: us-east-1                |
+----------------------------------+
                 |
                 ▼

      +------------------------+
      | Application Load       |
      | Balancer (ALB)         |
      | gabolir-alb            |
      +------------------------+
                 |
                 ▼

      +------------------------+
      | Target Group           |
      | gabolir-web-tg         |
      +------------------------+
                 |
                 ▼

      +------------------------+
      | Auto Scaling Group     |
      | gabolir-asg            |
      | Min: 2                |
      | Desired: 2            |
      | Max: 4                |
      +------------------------+
                 |
      -------------------------
      |                       |
      ▼                       ▼

+-------------------+   +-------------------+
| EC2 Instance      |   | EC2 Instance      |
| t3.micro          |   | t3.micro          |
| us-east-1a        |   | us-east-1c        |
| Apache HTTPD      |   | Apache HTTPD      |
| launch-wizard-2   |   | launch-wizard-2   |
+-------------------+   +-------------------+

      -------------------------
                 |
                 ▼

+----------------------------------+
| Custom Domain                    |
| www.gabolirmultinationals.com.ng |
+----------------------------------+

                 |
                 ▼

+----------------------------------+
| High Availability Web Platform   |
| Fault Tolerant                   |
| Auto Healing                     |
| Scalable Architecture            |
+----------------------------------+

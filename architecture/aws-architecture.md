
                                   Internet Users
                                          │
                                          ▼
                                   Amazon Route 53
                                          │
                                          ▼
                      ┌───────────────────────────────────┐
                      │  VPC: vpc-076a595462854afed       │
                      │         us-east-1                 │
                      └───────────────────────────────────┘
                                          │
                ┌─────────────────────────┴─────────────────────────┐
                │                                                   │
                ▼                                                   ▼

      Public Subnet (us-east-1a)                     Public Subnet (us-east-1c)
      subnet-0f68703f363f9b703                       subnet-014bdb077302ae732
                │                                                   │
                └─────────────────────────┬─────────────────────────┘
                                          │
                                          ▼

                      ┌───────────────────────────────────┐
                      │ Application Load Balancer         │
                      │        gabolir-alb                │
                      └───────────────────────────────────┘
                                          │
                                          ▼

                      ┌───────────────────────────────────┐
                      │ Target Group                      │
                      │ gabolir-web-tg                    │
                      └───────────────────────────────────┘
                                          │
                                          ▼

                      ┌───────────────────────────────────┐
                      │ Auto Scaling Group                │
                      │ gabolir-asg                       │
                      │ Min: 2                            │
                      │ Desired: 2                        │
                      │ Max: 4                            │
                      └───────────────────────────────────┘
                                          │
                     ┌────────────────────┴───────────────────┐
                     │                                        │
                     ▼                                        ▼

           EC2 Instance (t3.micro)                 EC2 Instance (t3.micro)
                us-east-1a                              us-east-1c
             Apache HTTPD                            Apache HTTPD
             launch-wizard-2                         launch-wizard-2

                     └────────────────────┬───────────────────┘
                                          │
                                          ▼

                          Amazon CloudWatch Monitoring

# AWS Associate Developer (DVA-C01)

Date: January (tentative)
Vendor: AWS

Main Source:

[Pass the AWS Developer Associate Exam With This Free 16-Hour Course](https://www.freecodecamp.org/news/pass-the-aws-developer-associate-exam-with-this-free-16-hour-course/)

- Video Bookmark: 26:44 (Deployment Policies)

Secondary Sources:

[](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf)

[](https://d1.awsstatic.com/whitepapers/DevOps/practicing-continuous-integration-continuous-delivery-on-AWS.pdf)

[](https://d1.awsstatic.com/whitepapers/microservices-on-aws.pdf)

[](https://d1.awsstatic.com/whitepapers/serverless-architectures-with-aws-lambda.pdf)

[](https://d1.awsstatic.com/whitepapers/optimizing-enterprise-economics-serverless-architectures.pdf)

[](https://d1.awsstatic.com/whitepapers/DevOps/running-containerized-microservices-on-aws.pdf)

[](https://d1.awsstatic.com/whitepapers/AWS_Blue_Green_Deployments.pdf)

Notes:

Composition of Exam:

- 22% deployment~ 14 questions
- 26% security ~ 17 questions
- 30% development with AWS Services ~ 20 questions
- 10% refactoring ~ 7 questions
- 12% Monitoring and Troubleshooting ~ 8 questions

Introduction to Elastic Beanstalk

Quickly deploy and manage web-apps on AWS without worrying about the underlying infrastructure (PaaS) 

What is a Platform as a Service?

A platform allowing customers to develop, run, and manage applications without the complexity of building and maintaining the infrastructure typically associated with developing and launching an app.

**Flow**:

Choose a platform

upload your code

Runs with little knowledge of the infrastructure

- Not recommended for "production" applications (large, enterprise companies)

Elastic Beanstalk is powered by a CloudFormation template setup for you:

- Elastic load balancer
- Autoscaling Groups
- RDS Database
- EC2 instance preconfigured (or custom) platforms
- Monitoring (CloudWatch, SNS)
- In-Place and Blue/Green deployment methodologies
- Security (rotates passwords)
Can run Dockerized environments

Supported Languages:

Ruby → Rails

Python → Django

PHP → Laravel

Tomcat → Spring

NodeJS → ExpressJS

Among many more of the common ones (Go, Docker, etc.)

Web vs Worker Environment

Beanstalk application comes in two environments: Web or Worker

![AWS%20Associate%20Developer%20(DVA-C01)%207cf726569eff442b9068f50cc411381c/Untitled.png](AWS%20Associate%20Developer%20(DVA-C01)%207cf726569eff442b9068f50cc411381c/Untitled.png)

Web Environment:

Creates an ASG

Creates an ELB

Web Environment Types:

Load Balanced Environment

![AWS%20Associate%20Developer%20(DVA-C01)%207cf726569eff442b9068f50cc411381c/Untitled%201.png](AWS%20Associate%20Developer%20(DVA-C01)%207cf726569eff442b9068f50cc411381c/Untitled%201.png)

Uses ASG and set to scale

Uses an ELB

Designed to scale

Single Instance Environment

Still uses an ASG but Desired Capacity set to 1 to ensure the server is always running

No ELB to save on cost

Public IP address has to be used to route traffic to the server

Worker Environment:

Creates an ASG

Creates an SQS Queue

Installs the Sqsd daemon on the EC2 instances

Creates CloudWatch alarm to dynamically scale instances based on health

Deployment Policies:
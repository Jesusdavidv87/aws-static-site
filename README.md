# AWS Static Website Architecture 🚀

## Overview
This project demonstrates how to design and deploy a secure, scalable, and cost-efficient static website using AWS services.

The goal is not just to host a website, but to apply real-world cloud architecture principles including security, performance optimization, and automated deployment.

---

## Architecture

**S3 (Storage) → CloudFront (CDN + HTTPS) → End Users**

Future extension:
**API Gateway → Lambda → Database (RDS / DynamoDB)**

---

## Key Components

- **Amazon S3**
  - Hosts static website content
  - Private bucket with restricted access

- **Amazon CloudFront**
  - Provides global content delivery (low latency)
  - Enforces HTTPS
  - Secures access to S3 via Origin Access Control (OAC)

- **IAM + OIDC (GitHub Actions)**
  - Enables secure CI/CD without storing credentials
  - Uses short-lived tokens and least privilege access

---

## Security Design

- S3 public access blocked
- Access restricted through CloudFront only
- IAM roles used instead of static credentials
- Principle of least privilege applied to all policies

---

## CI/CD (In Progress)

- GitHub Actions configured with OIDC
- Automated deployment to S3 on code changes
- No credentials stored in repository

---

## Business Impact

This architecture reflects how organizations deliver static content in production environments:

- **Improved performance** through CDN caching (CloudFront)
- **Enhanced security** by removing direct public access to storage
- **Cost efficiency** by using serverless infrastructure (no EC2 required)
- **Scalability** with global distribution and automatic scaling
- **Operational simplicity** through automated deployments

---

## Trade-offs & Design Decisions

- Chose **CloudFront + S3** over EC2:
  - Lower cost
  - Less operational overhead
  - Better scalability

- Used **OIDC instead of access keys**:
  - Eliminates credential risk
  - Improves security posture

- Kept architecture simple:
  - Easier to maintain and extend

---

## Live Demo

- S3 Website Endpoint:  
  http://aws-static-site-jesusdavidv87.s3-website-us-east-1.amazonaws.com

- CloudFront HTTPS Endpoint:  
  https://dvlfgfp2m78gv.cloudfront.net

---

## Key Learnings

- Secure architectures often require restricting default access patterns
- CDN integration significantly improves performance and user experience
- Identity and access design is critical for production-ready systems
- Automation is essential for scalability and consistency

---

## Next Steps

- Add custom domain using Route 53
- Extend backend with API Gateway + Lambda
- Integrate monitoring (CloudWatch)
- Improve CI/CD pipeline with testing and validation

---

## Author

Jesus Velasquez  
AWS Cloud Learner | Focused on Cloud Architecture, Scalability, and System Design

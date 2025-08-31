# AWS Static Website Project 🚀

## Project Goal
Host a static website on **Amazon S3** fronted by **CloudFront**, with future CI/CD via **GitHub Actions**. 
This repo will serve as evidence of hands-on AWS skills for Solutions Architect Associate prep.

## Day 1 Log (2025-08-28)
- Created GitHub repo `aws-static-site`
- Set project goals and structure
- Launched a Free Tier EC2 instance for practice and environment setup (SSH tested)

## Architecture (target for Week 1)
- S3 for static site hosting
- CloudFront for CDN + HTTPS
- IAM for least-privilege deployment access
- (Later) GitHub Actions to deploy on push

## Project Structure (initial)
```
aws-static-site/
├── index.html
└── README.md
```

## Next Steps
- Day 2: Create S3 bucket, enable static website hosting, upload `index.html`
- Day 3: Add CloudFront distribution
- Day 4+: Add GitHub Actions, screenshots, and a diagram

## Author
**Jesus Velasquez**

## Day 1 Achievements (2025-08-28)
- Completed 1.5 hrs of CLF course (Global Infra + Compute)
- Launched and connected to EC2 instance
- Verified environment with basic Linux commands:

- Created aws-static-site repo with starter files
- Added repo topics for discoverability
  
## Day 2 Achievements (2025-08-29)
- Completed Udemy CLF storage section (S3, EBS, EFS, Glacier).
- Created S3 bucket and enabled static website hosting.
- Applied bucket policy for public GET access.
- Uploaded `index.html` and verified website endpoint.
- ✅ Website live: http://aws-static-site-jesusdavidv87.s3-website-us-east-1.amazonaws.com

- ## Day 3 Achievements (2025-08-30)
- Deployed CloudFront distribution in front of S3.
- Configured Default Root Object (index.html).
- Applied OAC bucket policy to lock S3 bucket access to CloudFront only.
- Re-enabled Block Public Access on S3.
- Verified secure HTTPS site: https://dvlfgfp2m78gv.cloudfront.net

- Day 4 Log (2025-08-31)

Explored IAM basics (Skill Builder labs)

Set up IAM role with OIDC provider for GitHub Actions

Prepared GitHub Actions workflow for secure deploys

🔐 Secure GitHub → AWS Deployment with OIDC

This project uses GitHub Actions with AWS IAM OpenID Connect (OIDC) to securely deploy the static site to Amazon S3 and manage CloudFront.

Instead of storing long-lived AWS access keys, the GitHub workflow assumes a short-lived IAM role at build time. This follows AWS security best practices:

No static credentials stored in the repo

Least privilege access (limited to S3 + CloudFront for this project)

Automatic credential rotation handled by AWS



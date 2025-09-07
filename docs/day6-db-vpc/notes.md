## Day 6 – Databases & Networking  

### Databases
- **RDS**: Managed SQL (MySQL, PostgreSQL, etc.), handles backups, scaling, patching.  
- **DynamoDB**: NoSQL, serverless, pay-per-request, great for high-scale apps.  

### Networking
- **VPC (Virtual Private Cloud)**: Isolated network in AWS.  
  - Public subnet = resources accessible from internet (e.g., web server).  
  - Private subnet = internal-only (e.g., database).  
- **Route 53**: AWS DNS service to route domain names to resources.  

---

💡 **Key Idea**:  
Static website (S3) → CloudFront (CDN) → (Future: API Gateway + Lambda + DB inside VPC)

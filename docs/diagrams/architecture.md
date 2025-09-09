## Static Site Architecture (Week 1)

```mermaid
graph LR
  A[Developer - GitHub] -->|OIDC Assume Role| B(IAM Role)
  B -->|PutObject| C[S3 Static Site Bucket]
  C --> D[CloudFront Distribution]
  E[Route 53 (optional)] --> D
  D -->|HTTPS| F[End Users]

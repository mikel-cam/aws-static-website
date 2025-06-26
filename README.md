# AWS Static Website (Free Tier Safe)

This project hosts a static website on AWS using S3, CloudFront, and GitHub Actions for CI/CD — fully within AWS Free Tier limits.

## 📁 Architecture
- **Frontend:** HTML/CSS/JS
- **CI/CD:** GitHub Actions (multi-branch)
- **Hosting:** S3 buckets for dev, staging, and production
- **Security:** IAM policies, private S3 + CloudFront OAC
- **Monitoring:** CloudFront logs, CloudTrail, CloudWatch

## 🚀 Branch Workflow
| Branch        | Environment      |
|---------------|------------------|
| main          | Production       |
| staging       | Staging          |
| development   | Development      |
| feature/*     | Feature branches |

## 🛠️ Deployment
Each push triggers GitHub Actions to upload only changed files to the correct S3 bucket depending on the branch.

## ✅ Free Tier Features Used
- S3 (5 GB storage)
- CloudFront (1 TB bandwidth)
- GitHub Actions (2000 free min/month private)
- CloudTrail Event History

Summary: Actions & Features by Component

S3 (Amazon S3)
- Created 3 buckets: dev, staging, prod  - Uploaded HTML/CSS/JS  - Disabled public access  - Enabled bucket policy for CloudFront OAC
🔒 Secure storage of static site files  🚫 Prevent public access  📁 Multi-env hosting

CloudFront
- Set up distribution for each S3 bucket  - Enabled OAC (Origin Access Control)  - Linked error pages  - Set custom domain (optional)
🌍 Global content delivery  ⚡ Faster load times  🔐 Restricts S3 direct access

GitHub Actions
- Created CI/CD workflow per branch (main, staging, dev)  - Detect file changes  - Upload to S3 using AWS CLI  - Invalidate CloudFront cache
🤖 Automate deployment  🚀 Push on every commit  🎯 Ensure fresh files in CloudFront

IAM (AWS Identity & Access Mgmt)
- Created github-actions-deployer IAM user  - Assigned limited policy for S3, CloudFront, and logs  - Stored access keys in GitHub Secrets
🔐 Fine-grained access control  🧪 Least privilege for automation

Git (GitHub)
- Set up branches: main, staging, development, feature/login-page  - Promoted code via merges or file sync  - Added README and diagram
🧪 Isolate environments  📘 Clear documentation  🚀 Controlled deployment flow

CloudTrail
- Enabled Event History only (no S3 trail)
📜 Audit who accessed or modified AWS resources  💸 100% free with no storage fees

CloudWatch
- Enabled default CloudFront metrics
📊 Monitor performance, traffic, errors

S3 Logs (for CloudFront)
- Enabled logging on CloudFront to a separate S3 bucket
📈 Monitor requests, user agents, troubleshooting

README & Diagram
- Created README.md with project overview  - Designed and committed architecture diagram
🧠 Improves documentation  ✅ Portfolio-ready repo

---
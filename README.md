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

---
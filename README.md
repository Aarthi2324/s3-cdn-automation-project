# S3 CDN Automation Pipeline

A CI/CD pipeline that automates static website deployment to Amazon S3 using GitHub Actions and delivers content through Amazon CloudFront.

## Tech Stack
- Amazon S3
- Amazon CloudFront
- GitHub Actions
- Python
- Bash
- AWS IAM

## Key Features
- Automated website deployment
- HTML validation before deployment
- CloudFront cache invalidation
- Post-deployment health checks
- Backup and rollback on deployment failure

## Deployment Steps
1. Push website changes to the configured GitHub branch.
2. GitHub Actions validates the HTML file.
3. The workflow uploads the website to Amazon S3.
4. CloudFront cache invalidation refreshes the content.
5. A health check verifies the deployed website.
6. The successful version is saved as a backup.

## Rollback Steps
1. If deployment or the health check fails, the workflow attempts rollback.
2. The previous backup version is restored to S3.
3. CloudFront cache invalidation is triggered again.
4. Verify that the previous website version is accessible.

## Workflow
Developer → GitHub Actions → HTML Validation → S3 Deployment → CloudFront → Health Check → Backup / Rollback

## Purpose
To reduce manual deployment effort and improve website deployment reliability through automated validation, health checks, and recovery.




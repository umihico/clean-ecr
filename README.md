# Clean ECR

Wipe untagged images weekly

## Local execution with another profile

```bash
export AWS_PROFILE=default # or change to another
circleci local execute --job batch \
  -e AWS_ACCESS_KEY_ID=$(aws configure get aws_access_key_id) \
  -e AWS_SECRET_ACCESS_KEY=$(aws configure get aws_secret_access_key) \
  -e AWS_ACCOUNT_ID=$(aws sts get-caller-identity --query Account --output text) \
  -e AWS_DEFAULT_REGION=$(aws configure get region) \
  -e AWS_REGION=$(aws configure get region)
```

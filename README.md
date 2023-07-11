# AWS Amplify with GitHub Actions integration

## Description
GitHub Actions workflow that integrates with AWS Amplify, showing logs and build/deploy status of an AWS Amplify application

## Prerequisites
Before running the workflow, you will need to set the following secrets in your GitHub repository:
- `AWS_ACCESS_KEY_ID`: The AWS Access Key ID of your IAM user.
- `AWS_SECRET_ACCESS_KEY`: The AWS Secret Access Key of your IAM user.
- `AWS_DEFAULT_REGION`: The region where your AWS Amplify app is located.
- `AWS_AMPLIFY_APP_ID`: The ID of your AWS Amplify application.

## IAM Policy
For the workflow to work well, your IAM user will need the following policy/permission:
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "amplify:GetJob",
                "amplify:StartJob"
            ],
            "Resource": "arn:aws:amplify:{your-region}:{your-account-id}:apps/*/branches/*/jobs/*"
        }
    ]
}
```
# Deploying Jenkins Pipeline with CloudFormation

This script installs a multi AZ Jenkins Pipeline on ec2 with auto-scaling for high-availability.

## Setup

Run this script in AWS console as a CloudFormation template ("Template is ready / Upload template / Choose file") or run the following command:
```
aws cloudformation deploy \
--template-file jenkins-multiaz.yaml \
--stack-name jenkins \
--parameter-overrides JenkinsAdminPassword=mysecretpwd KeyName=Ireland
```

After installation, get public ip from AWS Console ec2 page and go to
```
http://<public ip>:8080
```
(No VPN and it has to be http, not https!)

**Warning: this setup is not secure (no https, ingress is allowed for everybody, not the latest AMI and Jenkins package etc.)**

## Cleanup
```
aws cloudformation delete-stack --stack-name jenkins
```

# Deploying Jenkins Pipeline with CloudFormation

This script installs a Jenkins Pipeline on ec2 with auto-scaling for high-availability.

Run this script in AWS console as a CloudFormation template.
After installation, go to
```
http://<public ip>:8080
```
(it has to be http, not https!)

Warning: this setup is not secure (no https, ingress is allowed for everybody etc.)
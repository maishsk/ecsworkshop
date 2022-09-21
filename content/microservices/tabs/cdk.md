---
title: "Embedded tab content"
disableToc: true
hidden: true
---

### Install and setup prerequisites

```
# Install prerequisite packages
sudo yum -y install jq nodejs python36 siege

<!-- # Install packages
pip3 install --user --upgrade awscli awslogs 
-->

# Setting environment variables required to communicate with AWS API's via the cli tools
echo "export AWS_DEFAULT_REGION=$(curl -s 169.254.169.254/latest/dynamic/instance-identity/document | jq -r .region)" >> ~/.bashrc
echo "export AWS_REGION=\$AWS_DEFAULT_REGION" >> ~/.bashrc
echo "export AWS_ACCOUNT_ID=$(aws sts get-caller-identity --query Account --output text)" >> ~/.bashrc
source ~/.bashrc
```

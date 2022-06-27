---
title: "Configure the Google Cloud Platform Permissions for your Agent Assist Project"
chapter: false
weight: 60
---

## Configure the Google Cloud Platform Permissions for your Agent Assist Project

1. Navigate back to the Genesys Cloud CX integrations page and find the Agent Assist integration that we set up earlier. 
    - On the Details page, copy to your clipboard the Google-Cloud-Service-Account
    ![Google Cloud Service Account](/images/googleCloudServiceAccount.jpg)
2. Navigate back to your Google Cloud platform account and then to the IAM section. Click add new and then add the Google-Cloud-Service-Account that you just copied as the member.
    - Under select role, give the service account the following roles
        - DialogFlow API Admin
        - DialogFlow API Client
        ![IAM Service Account](/images/IAMServiceAccount.jpg)
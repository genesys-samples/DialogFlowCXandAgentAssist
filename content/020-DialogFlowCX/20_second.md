---
title: "Integration Setup"
chapter: false
weight: 20
---

## Integration Setup

1. In the Google Cloud Platform console, create a new project and then create a service account for the project.
    - A Google Cloud project allows you to organize all your Google Cloud resources. As an example, you might have one Google Cloud project for your marketing team and another project for your sales team. Projects simply allow you to keep resources separated. 
    - A service account is a special type of account that is used to execute applications and run automated services. Service accounts allow you to grant permissions to different applications or resources in your Google environment. As an example, you might want a DialogFlow CX agent to have access to trigger Google Cloud Functions, but you wouldn't want them to be able to deactivate a virtual machine.
2. Grant the following roles to the service account: "DialogFlow API Client", "DialogFlow API Reader", and "DialogFlow Conversation Manager"
3. Create a service account key and download the JSON version of it.
4. Go to the Genesys Cloud CX integrations page and find your DialogFlow CX integration. Within that integration, navigate to the credentials tab and click configure. 
    - Now input the corresponding values from the JSON file that you downloaded in the previous step. 

#### Video showing the steps above
https://youtu.be/nvKh-yNxIKQ 
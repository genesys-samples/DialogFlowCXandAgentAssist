---
title: "Integration Setup"
chapter: false
weight: 20
---

## Integration Setup
1. Create a project and a service account in your Google Cloud Platform console
    - You can also use the project that you created in the DialogFlow CX section of this workshop. Just create a new service account within that project.
2. Enable in your project the "Dialogflow API" and the "Data Labeling API"
    - https://cloud.google.com/dialogflow/es/docs/quick/setup#api 
    - https://cloud.google.com/ai-platform/data-labeling/docs/before-you-begin 
3. Navigate to the Dialogflow console for your project and then upgrade to the Pay as You Go DialogFlow Essentials Package
    - https://dialogflow.cloud.google.com/#/agent/${your-project-id}
    ![Pay as you Go](/images/payAsYouGo.jpg)
4. Install the Agent Assist with Google Cloud integration into your Genesys Cloud CX admin console
![Agent Assist Integration](/images/agentAssistIntegration.jpg)
5. Edit the integration and add the Project ID to the properties tab
![Add Project ID](/images/addProjectID.jpg)
6. Click save to automatically trigger allow-listing for the Google Cloud platform project. The allow listing process can take up to 48 hours, but the Genesys Cloud onboarding team will inform you when the request executes successfully. 
    - In other words, wait. Once you get the notification that the request is successful, you can then activate the integration and then continue on with this workshop. 
    - If you wait for more than 72 hours and you haven't been notified that the request was successful, please reach out to Travis Coleman at travis.coleman@genesys.com with your org ID and region. 
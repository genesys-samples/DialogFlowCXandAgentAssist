---
title: "Integration Setup"
chapter: false
weight: 20
---

## Integration Setup
1. Create a project and a service account in your Google Cloud Cloud Platform console
    - You can also use the project that you created in the Dialogflow CX section of this workshop. Just create a new service account within that project.
2. Enable in your project the "Dialogflow API" and the "Data Labeling API"
    - https://cloud.Google Cloud.com/Dialogflow/es/docs/quick/setup#api 
    - https://cloud.Google Cloud.com/ai-platform/data-labeling/docs/before-you-begin 
3. Navigate to the Dialogflow console for your project and then upgrade to the Pay as You Go Dialogflow Essentials Package
    - https://Dialogflow.cloud.google.com/#/agent/${your-project-id}
    ![Pay as you Go](/images/payAsYouGo.jpg)
4. Install the Agent Assist with Google Cloud Cloud integration into your Genesys Cloud CX admin console
![Agent Assist Integration](/images/agentAssistIntegration.jpg)
5. Edit the integration and add the Project ID to the properties tab
![Add Project ID](/images/addProjectID.jpg)
6. Click save to automatically trigger allow-listing for the Google Cloud Cloud platform project. The allow listing process can take up to 48 hours, but the Genesys Cloud onboarding team will inform you when the request executes successfully. 
    - In other words, wait. Once you get the notification that the request is successful, you can then activate the integration and then continue on with this workshop. 
    - If you wait for more than 72 hours and you haven't been notified that the request was successful, please reach out to workshops@genesys.com with your org ID and region. 


If you wish to watch a video of these steps, follow this link: https://youtu.be/u-M6HkNf758
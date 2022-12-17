---
title: "Configure los permisos de Google Cloud Platform para su proyecto de Agent Assist"
chapter: false
weight: 60
---

## Configure los permisos de Google Cloud Platform para su proyecto de Agent Assist

1. Navigate back to the Genesys Cloud CX integrations page and find the Agent Assist integration that we set up earlier. 
    - On the Details page, copy to your clipboard the Google Cloud-Cloud-Service-Account
    ![Google Cloud Service Account](/images/googleCloudServiceAccount.jpg)
2. Navigate back to your Google Cloud Cloud platform account and then to the IAM section. Click add new and then add the Google-Cloud-Service-Account that you just copied as the member. However, you only need to input a portion of the Google-Cloud-Service Account which you can see in this screenshot.
![Service Account Snipit](/images/serviceAccountSnip.jpg)
    - Under select role, give the service account the following roles
        - Dialogflow API Admin
        - Dialogflow API Client
        ![IAM Service Account](/images/IAMServiceAccount.jpg)


1. Vuelva a la página de integraciones de Genesys Cloud CX y busque la integración de Agent Assist que configuramos anteriormente. 
    - 2. En la página Detalles, copie en el portapapeles la cuenta de servicios en la nube de Google
    ![Google Cloud Service Account](/images/googleCloudServiceAccount.jpg)
2. Navegue de nuevo a su cuenta de la plataforma Google Cloud y luego a la sección IAM. Haga clic en Añadir nuevo y, a continuación, añada la cuenta de servicio de Google Cloud que acaba de copiar como miembro. Sin embargo, sólo tiene que introducir una parte de la cuenta de servicio de Google Cloud que puede ver en esta captura de pantalla.
![Service Account Snipit](/images/serviceAccountSnip.jpg)
    - En Seleccionar función, asigne a la cuenta de servicio las siguientes funciones
        - Administrador de la API de Dialogflow (Dialogflow API Admin)
        - Cliente de API de Dialogflow (Dialogflow API Client)
        ![IAM Service Account](/images/IAMServiceAccount.jpg)
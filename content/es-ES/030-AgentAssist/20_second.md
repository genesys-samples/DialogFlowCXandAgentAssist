---
title: "Configuración de la integración"
chapter: false
weight: 20
---

## Configuración de la integración
1. Cree un proyecto y una cuenta de servicio en su consola de Google Cloud Cloud Platform.
    - También puede utilizar el proyecto que creó en la sección Dialogflow CX de este taller. Solo tiene que crear una nueva cuenta de servicio dentro de ese proyecto.
2. Habilite en su proyecto la "API de Dialogflow" y la "API de etiquetado de datos"
    - https://cloud.google.com/dialogflow/es/docs/quick/setup#api
    - https://cloud.google.com/ai-platform/data-labeling/docs/before-you-begin
3. Navegue a la consola Dialogflow para su proyecto y luego actualice al paquete Dialogflow Essentials Pay as You Go
    - https://Dialogflow.cloud.google.com/#/agent/${your-project-id}
    ![Pay as you Go](/images/payAsYouGo.jpg)
4. Instale la integración de Agent Assist con Google Cloud en su consola de administración de Genesys Cloud CX
![Agent Assist Integration](/images/agentAssistIntegration.jpg)
5. Edite la integración y añada el ID de proyecto a la pestaña de propiedades
![Add Project ID](/images/addProjectID.jpg)
6. Haga clic en Guardar para activar automáticamente la inclusión en la lista permitida del proyecto de la plataforma Google Cloud. El proceso de inclusión en la lista de permitidos puede tardar hasta 48 horas, pero el equipo de incorporación de Genesys Cloud le informará cuando la solicitud se ejecute correctamente. 
    - En otras palabras, espere. Una vez que reciba la notificación de que la solicitud se ha realizado correctamente, podrá activar la integración y continuar con este taller. 
    - Si espera más de 72 horas y no ha recibido la notificación de que la solicitud se ha realizado correctamente, póngase en contacto con workshops@genesys.com indicando su ID de organización y región. 


Si desea ver un vídeo sobre estos pasos, siga este enlace: https://youtu.be/u-M6HkNf758
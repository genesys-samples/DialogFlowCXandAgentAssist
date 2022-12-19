---
title: "Setup de la integración"
chapter: false
weight: 20
---

## Setup de la integración

1. En la consola de Google Cloud Platform, cree un nuevo proyecto y, a continuación, cree una cuenta de servicio para el proyecto.
    - Un proyecto de Google Cloud Platform le permite organizar todos sus recursos de Google Cloud Platform. Por ejemplo, puede tener un proyecto de Google Cloud Platform para su equipo de marketing y otro para su equipo de ventas. Los proyectos simplemente le permiten mantener los recursos separados. 
    - Una cuenta de servicio es un tipo especial de cuenta que se utiliza para ejecutar aplicaciones y ejecutar servicios automatizados. Las cuentas de servicio le permiten conceder permisos a diferentes aplicaciones o recursos en su entorno de Google Cloud. Como ejemplo, es posible que desee que un agente de Dialogflow CX tenga acceso para activar las funciones de Google Cloud Cloud, pero no le gustaría que pudieran desactivar una máquina virtual.
2. Conceda las siguientes funciones a la cuenta de servicio: "Dialogflow API Client", "Dialogflow API Reader", y "Dialogflow Conversation Manager".
3. Cree una clave de cuenta de servicio y descargue la versión JSON de la misma.
4. Vaya a la página de integraciones de Genesys Cloud CX y busque su integración Dialogflow CX. Dentro de esa integración, vaya a la pestaña de credenciales y haga clic en configurar. 
    - Ahora introduzca los valores correspondientes del archivo JSON que descargó en el paso anterior. 

#### Vídeo que muestra los pasos anteriores
https://youtu.be/nvKh-yNxIKQ 
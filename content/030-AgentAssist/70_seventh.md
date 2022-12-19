---
title: "Creación de su Asistente de Agente en Genesys Cloud CX"
chapter: false
weight: 70
---

## Creación de su Asistente de Agente (Agent Assist) en Genesys Cloud CX
1. Navegue a su consola de administración de Genesys Cloud CX. El primer paso que debemos dar es asegurarnos de que nuestro usuario tiene los permisos correctos para añadir Asistentes de Agente. Cree un nuevo rol o edite un rol existente con los siguientes permisos. Una vez que tenga el rol, añádalo a su usuario.
    - Asistentes > Asistente > Añadir
    - Asistentes > Asistente > Editar
    - Asistentes > Asistente > Ver
    - Asistentes > Cola > Añadir
    - Asistentes > Cola > Editar
    - Asistentes > Cola > Ver
    - Asistentes > Cola > Eliminar
    - Telefonía > Plugin > Todos los permisos
2. Es posible que tenga que actualizar la pantalla después de dar a su usuario los permisos, pero ahora debería tener un botón de Asistente bajo Contact Center en la página de administración que no estaba allí antes. Haga clic en la opción Asistente.
![Assistants Admin](/images/assistantsAdmin.jpg)
3. Haga clic para añadir un nuevo asistente. Asigne al Asistente el nombre de "Candy Shop" y pegue el ID de integración del perfil de conversación que habíamos copiado en un paso anterior. Pulsa guardar. 
![New Assistant](/images/newAssistant.jpg)
4. Una vez pulses guardar, aparecerá una nueva pestaña en la parte superior para que asignes este asistente a colas. Asigna este asistente a una cola de la que forme parte tu usuario, así podremos probar lo que hemos construido.
![Assign to Queues](/images/assignToQueues.jpg)

## Probar el Asistente de Agente (Agent Assist)

Nota: Debe tener la grabación de línea habilitada en la troncal para que esto funcione. Si no lo tiene habilitado, siga estos pasos para completarlo. https://help.mypurecloud.com/articles/enable-line-recording/
Finalmente estamos en el último paso, ¡donde podemos ver la integración en acción!
1. Hay algunos prerrequisitos que necesita para poder probar Agent Assist. Estos son: 
    - Su usuario forma parte de una cola (la misma cola que tiene asignado el Asistente)
        - https://help.mypurecloud.com/articles/create-queue/ 
    - Su usuario tiene los permisos adecuados para manejar una interacción de voz y un teléfono asignado a ellos   
        - El "Genesys Cloud User" (También puede llamarse PureCloud User) debería darle los permisos adecuados
        - https://help.mypurecloud.com/articles/configure-the-genesys-cloud-webrtc-phone/ 
            - Nota: es posible que su org ya tenga creada la configuración base
    - Usted tiene un flujo de architect que transfiere a la cola a la cual está asignado
        - https://help.mypurecloud.com/articles/create-call-flow/
    - Tiene una ruta de llamada configurada que conecta un número de teléfono con el flujo de arquitecto que transfiere a su cola.
        - https://help.mypurecloud.com/articles/add-a-call-route/


2. Ahora es el momento de ponerse el sombrero de agente y probar el asistente que acabamos de crear. Primero navegue hasta el panel de Interacciones y luego vaya a "En cola"
![On Queue](/images/onQueue.jpg)
3. Llame al número asignado a la ruta de llamada que conecta con su flujo de architect y consiga que la llamada se transfiera a su cola. Acepte la interacción. 
    - Sugerencia: es posible que desee silenciar al agente. La proximidad de los altavoces de su teléfono móvil y de su teléfono webRTC puede provocar eco. 
    ![Mute](/images/mute.jpg)
4. Haga clic en el control de llamadas del asistente y abra también la sección de transcripción.
![Assistant Call Control](/images/assistantCallControl.jpg)
5. En el teléfono desde el que está llamando haga las siguientes preguntas y confirme que el Asistente de Agente está sugiriendo los artículos correctos o FAQs. Ayude también a entrenar al Asistente marcando los artículos/FAQ relevantes o irrelevantes a medida que vayan apareciendo.
    - Empecemos con las FAQ. Como cliente, pregunte lo siguiente 
        - "¿Cuándo está abierta su tienda?" 
        - "¿Ofrecen dulces veganos?" 
        - ¿Cuál es el dulce más popular? 
    - Ahora a los artículos de conocimiento (estos los seleccionará en el enlace y le abrirá otra pestaña)
        - "Quiero comprobar el estado de mi entrega"
        - "Necesito presentar una reclamación"
        - "Tengo un pedido especial"
        ![Mark Relevant](/images/markRelevant.jpg)

Si quiere ver un video de los pasos de esta sección clic aquí. https://youtu.be/7pw1l1o8om4
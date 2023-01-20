---
title: "Invocación del agente Dialogflow CX en un flujo de architect"
chapter: false
weight: 40
---

## Invocación del agente Dialogflow CX en un flujo de architect
Llegamos al último paso. Ahora que el Dialogflow CX Agent está completo, podemos llamarlo en un flujo de architect. Esto realmente completará nuestra integración de extremo a extremo de Google Cloud a Genesys con todas las capacidades de Google Cloud Dialogflow CX y Genesys Cloud CX Architect disponibles para nuestra tienda de golosinas. Vamos a hacer esto bastante simple para los propósitos de hoy. Por favor, síganos. 

- Abra Architect en su aplicación Genesys Cloud CX y navegue para crear un nuevo flujo de mensajes. Dele un nombre descriptivo y haga clic en crear. 
![Create Message Flow](/images/createMessageFlow.jpg)
- En el bloque de estado inicial, arrastre un bloque "Call Dialogflow CX Bot" al principio del estado. De la lista desplegable, elija el Agente que acabamos de crear.
![DialogflowCX Architect Block](/images/dialogFlowCXArchitectBlock.jpg)
- Ahora obtendremos los datos de los parámetros de la sesión de Dialogflow CX. 
    - En el mismo bloque, en parámetros de sesión, añada dos salidas. Nombre las salidas Candy y Quantity ya que esos fueron los nombres de los parámetros que creamos en el lado de Google Cloud. Asigne a esos parámetros nombres de variables para que podamos aprovecharlos en nuestro flujo de arquitecto.
    ![Architect Parameters](/images/architectParameters.jpg)
- En este punto, nos damos cuenta de que queremos añadir una opción para que un cliente hable con un humano en vivo. Volvamos al agente Dialogflow CX que creamos antes y añadamos una nueva ruta desde el bloque de inicio. 
    - Usando la funcionalidad inline que aprendimos antes, cree una nueva intención llamada LiveAgent con algunas frases de entrenamiento que sean aplicables. 
     ![Live Agent Intent](/images/liveAgentIntent.jpg)
    - Mientras sigue trabajando dentro de esa ruta añada una nueva opción de diálogo bajo fulfillment. Elija "live agent handoff" como tipo y añada este texto al cuerpo.
        - {
"Intent": "LiveAgent"
}
![Live Agent Handoff](/images/liveAgentHandoff.jpg)
    - Mientras seguimos editando esa ruta, hacemos la transición a una nueva página y establecemos esa página como Fin de sesión (End Session). Finalizar sesión nos permitirá salir del agente Dialogflow CX y pasar de nuevo a architect.
    ![End Session](/images/endSession.jpg)
- Navegue de nuevo a architect (es posible que tenga que pulsar guardar y luego actualizar la pantalla, ya que acabamos de hacer cambios en nuestro agente de Dialogflow CX) 
    - De vuelta en su bloque Dialogflow CX bot, añada alguna salida en la sección Live Agent Handoff Metadata. El nombre de la clave debe coincidir con el nombre de la clave que hemos creado en el paso anterior. Para el nombre de la variable, establezca un nombre para ser referenciado desde dentro de Architect. 
    ![Architect Live Agent Handoff](/images/architectLiveAgentHandoff.jpg)
    - Bajo la ruta de éxito en Architect, arrastre un bloque de decisión y tomemos una decisión sobre si nuestra variable para la intención es igual a LiveAgent (consejo: si ha nombrado su intención de otra manera en Google Cloud, tendrá que tratar de que coincida con ese nombre en Architect)
    ![Intent Decision](/images/intentDecision.jpg)
    - Si la decisión es afirmativa, transfiéralo a una cola de la que sea miembro. Por último, añada una desconexión al final del flujo y publique!
    ![Final Architect Flow](/images/finalArchitectFlow.jpg)
    - Ahora vamos a probarlo. Necesitará crear una configuración y despliegue de web messenger. Esta no es la lección del taller de hoy, así que si aún no lo tiene configurado en su organización, siga las siguientes instrucciones. 
        - Configuración - https://help.mypurecloud.com/articles/configure-messenger/ 
        - Despliegue - https://help.mypurecloud.com/articles/deploy-messenger/
    - Último paso! Navegue hasta nuestras herramientas para desarrolladores de mensajería web (web messenger developer tools) en el centro de desarrolladores y elija la implementación que ha creado.. https://developer.genesys.cloud/devapps/web-chat-messenger 
    ![Web Messaging Tool](/images/webMessagingTool.jpg)
    - Repasa esta conversación. 
        - Usted: "¡Hola!"
        - Bot: "Gracias por charlar con la tienda de golosinas. ¿En qué podemos ayudarte?"
        - Usted: "Encargar caramelos"
        - Bot: "¿Qué tipo de caramelos quieres pedir?".
        - Usted: Elige aquí el tipo de caramelo que quieras
        - Bot: "¿Cuántos *tipo de caramelo* quieres?
        - Usted: Ponga aquí cualquier número
        - Bot: "¡Tendremos su pedido de *cantidad* *tipo de caramelo* listo en dos días laborables!"
        - Usted: "¿Cuál es su horario?" 
        - Bot: "Nuestra tienda está abierta de lunes a sábado de 11 a 21 horas".
        - Usted: "Hablar con un agente"
    - Esto devolverá la interacción al architect y la enviará a nuestra cola. Debería poder gestionar la interacción desde el panel de interacción yendo a la cola y aceptando la interacción. 

También puede ver un vídeo sobre estos pasos aquí https://youtu.be/AoCeX5RjT0Y

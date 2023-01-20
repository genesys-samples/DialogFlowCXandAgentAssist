---
title: "Creación de un agente Dialogflow CX"
chapter: false
weight: 30
---
## Terminología
- Agentes - Agente es el término de Dialogflow para bot. Un agente es un módulo de comprensión del lenguaje natural que entiende los matices del lenguaje humano. Usted diseña y construye un agente Dialogflow para manejar los tipos de conversaciones requeridas para su sistema.
- Flujos - Se utilizan para definir temas y las rutas conversacionales asociadas. Aquí hay un ejemplo de diferentes flujos que podrían ser construidos para un agente de entrega de pizza.
Flujos de Entrega de Pizza](/images/PizzaDeliveryFlows.jpg)
- Páginas - Las páginas están configuradas para recoger información del usuario final que es relevante para el estado conversacional representado por la página. Vea el siguiente ejemplo de diferentes páginas en azul que podrían utilizarse para un flujo de Pedido de Comida. 
Páginas de pedidos de comida](/images/foodOrderPages.jpg)
- Tipos de entidad y parámetros - Si está familiarizado con otros motores bot, puede que conozca el término ranuras y tipos de ranuras. Los tipos de entidad y los parámetros son esencialmente lo mismo. Los tipos de entidad controlan cómo se pueden introducir los datos de los usuarios finales. Con los tipos de entidad, muchos vienen predefinidos como la Secuencia Numérica. Los tipos de entidad que vienen predefinidos se llaman entidades del sistema y los tipos de entidad que usted crea se llaman entidades personalizadas. Por ejemplo, puede crear un tipo de entidad personalizado para los ingredientes de la pizza que sólo acepte una lista predefinida de ingredientes. Los parámetros capturan y referencian valores que han sido suministrados por el usuario final. A cada parámetro se le asigna un tipo de entidad. Por ejemplo, el parámetro número de cuenta podría tener un tipo de entidad de secuencia numérica. 
- Formularios - Se construye un formulario para cada página y es una lista de parámetros que deben ser recogidos del usuario final para la página.
- Intentos / Intenciones (Intents) - Un intento categoriza la intención de un usuario basándose en datos llamados frases de entrenamiento. Las frases de entrenamiento son ejemplos de frases que los usuarios finales podrían escribir o decir y que coincidirían con la intención.
- Cumplimiento - El cumplimiento permite al agente virtual responder a las preguntas de los usuarios finales, solicitar información o finalizar una sesión. Es posible llamar a múltiples cumplimientos durante un turno.
- Controladores de estado / State Handlers - Se utilizan para controlar la conversación creando respuestas para los usuarios finales y/o cambiando la página actual.

Página de referencia - https://cloud.google.com/dialogflow/cx/docs/basics


## Construyendo un Agente Dialogflow CX
Hoy vamos a construir un agente virtual para una tienda de caramelos. La tienda de dulces espera utilizar Dialogflow CX para lograr dos cosas: 1. Permitir a los clientes realizar pedidos y 2. Dar a conocer el horario de la tienda. ¡Manos a la obra! Intente seguir los pasos que se indican a continuación o vea el vídeo al final de esta página.

- Navegue a la consola de Google Cloud CCAI y asegúrese de que está en el proyecto que creó en la sección anterior. 
    - https://dialogflow.cloud.google.com/cx/projects
- Si recibe este mensaje cuando accede al enlace, habilite la API.
![EnableAPI](/images/EnableAPI.jpg)
- Cree un nuevo agente y dele un nombre descriptivo como "Candy Shop Bot".
- La primera tarea que haremos es editar la Intención de Bienvenida por Defecto. Haga clic en el botón de inicio en el centro de la página y luego en Default Welcome Intent. En cumplimiento, vamos a eliminar las frases por defecto y añadir las nuestras; "Gracias por chatear con la tienda de caramelos. ¿En qué podemos ayudarle?" Asegúrese de hacer clic en Guardar. 
![Candy Shop Hello](/images/candyShopHello.jpg)
- Antes de pasar al siguiente paso, vamos a repasar la herramienta Agente de prueba. En la parte superior derecha, haga clic en agente de prueba. Si dice hola, ¡deberías recibir la respuesta que acabamos de crear!
[Test Agent](/images/testAgent.jpg)

Ahora vamos a crear un par de intenciones (intents) y páginas. Puede crear intents de dos maneras: desde la pestaña de gestión o en línea. Le mostraremos ambas formas. Las páginas pueden ser creadas desde la pestaña de construcción o en línea. Primero crearemos una intent desde la pestaña Gestionar y una página desde la pestaña Construir.
- Seleccione la pestaña Gestionar > Intenciones > Crear
- Nombre esta intención store.hours
- Introduzca al menos 5 frases de entrenamiento. Aquí hay dos ejemplos.
    - ¿Cuándo está abierta su tienda? 
    - ¿Cuál es su horario?
    - Asegúrese de pulsar Guardar después de añadir las frases de formación.
- Vuelva a la pestaña "Crear" y haga clic en el signo + para crear una nueva página llamada "Hours" (Horas).
- Pase el ratón por encima de la página Horas recién creada y haga clic en los 3 puntos y luego en Editar
    - Edite el campo de cumplimiento e introduzca un texto que describa el horario de su tienda de golosinas. Por ejemplo, "Nuestra tienda está abierta de lunes a sábado de 11 a 21 horas".
    - Asegúrese de pulsar Guardar tanto en el campo de cumplimiento como en la página. 
- Navegue de nuevo al Flujo de Inicio Predeterminado y pulse el bloque Inicio
    - Cree una nueva ruta y elija store.hours en el desplegable de intención y en la sección de transición elija la página Hours. 
- Ahora vamos a crear una intención y una página utilizando la funcionalidad inline
    - Haga clic en el bloque de inicio en Flujo de inicio predeterminado y luego en + para añadir una nueva ruta.
    - En la lista desplegable de intent haga clic en + nuevo Intent, lo que le permitirá crear una nueva intención directamente desde aquí
    ![Inline New Intent](/images/inlineNewIntent.jpg)
        - Nombre su nueva intención “Order Candy” ("Pedir caramelos") y añada algunas frases de entrenamiento de lo que un cliente podría decir si quiere pedir caramelos. En las frases de entrenamiento, añada las siguientes frases
            - pedir caramelos
            - hacer un nuevo pedido
            - quiero caramelos
            - quiero 500 chupa-chups
            - quiero comprar 10 caramelos de goma
        - Observe que se crea automáticamente un parámetro al introducir las frases de entrenamiento. Google Cloud reconoce, basándose en las frases de entrenamiento introducidas, que va a necesitar reunir la cantidad de caramelos como parámetro para esta intención. Enseguida hablaremos más sobre la adición de parámetros.
        ![Parameter Autopopulate](/images/parameterAutopopulate.jpg)
    - Mientras seguimos editando la ruta, navegamos hasta la sección de transición y ahora vamos a crear una nueva página utilizando la funcionalidad inline. 
    ![Inline New Page](/images/inlineNewPage.jpg)
        - nombre esta página “New Order” ("Nueva Orden") y, a continuación, guarde su ruta
- Comprobación rápida - en este punto, su editor gráfico debería tener este aspecto. 
![Graphical Editor Check In](/images/graphicalEditorCheckIn.jpg)


A continuación tenemos que añadir parámetros a nuestra página de Nueva Orden. Como se mencionó en las secciones de terminología, los parámetros deben ser de un tipo de entidad. Hay entidades del sistema que vienen precargadas y luego se pueden crear entidades personalizadas para tipos de datos personalizados. En nuestro escenario, recogeremos el tipo de caramelo que quieren pedir (entidad personalizada) y la cantidad de ese caramelo que quieren pedir. 
- Primero vamos a crear el nuevo tipo de entidad personalizada para el tipo de dulce. Nuestra tienda vende 5 tipos diferentes de caramelos: jawbreakers, gumdrops, suckers, gummy bears y jelly beans.
    - Vaya a la pestaña Gestionar > Tipos de entidad > y cree un nuevo tipo de entidad personalizado llamado candy_Types (Tipos_de_caramelos). En la sección de entidades de esta página, añada los 5 tipos de caramelos enumerados anteriormente y los sinónimos correspondientes que se le ocurran. Asegúrese de pulsar Guardar.
    ![Candy Type Entity](/images/candyTypeEntity.jpg)
- Ahora que tenemos nuestro tipo de entidad personalizada, podemos añadir nuestros parámetros a nuestra página de New Order (Nuevo Pedido). 
    - Navegue de nuevo a Construir y luego haga clic en la página Nuevo Pedido en el constructor gráfico. 
    - Haga clic en el signo + para crear un nuevo parámetro.
    - Nombre el parámetro "Candy"(Caramelo) y en el desplegable de tipo de entidad encuentre el tipo de entidad personalizada que acabamos de crear. Por último, en la sección Initial prompt fulfillment, escriba "¿Qué tipo de caramelo quiere pedir?". Después, pulse Guardar.
    ![Candy Parameter](/images/candyParameter.jpg)
    - Vuelva a pulsar el + para crear otro parámetro. Esta vez, recogeremos la cantidad que quieren pedir.
        - Para el nombre de visualización, escriba Cantidad y para el tipo de entidad elija @sys.number. 
        - Para el cumplimiento de la consulta inicial, escriba "¿Cuántos $session.params.Candy desea?".
        - La variable $session.params.Candy introducirá el tipo de caramelo que nos hayan proporcionado, por ejemplo "¿Cuántos caramelos quiere?".
Por último, crearemos una página de confirmación del pedido y pasaremos a esa página utilizando una condición que compruebe si se han rellenado todos los parámetros del nuevo pedido.
- Primero cree una nueva página y nómbrela Confirmación de Pedido. 
- Haga clic en la página y añada un cumplimiento de entrada que diga "¡Tendremos listo su pedido de $session.params.Quantity $session.params.Candy en dos días laborables!".
- Vuelva a la interfaz gráfica Flujo de inicio predeterminado y haga clic en la página Nuevo pedido. 
    - Haga clic en el signo + para añadir una nueva ruta. 
    - Añada una condición para comprobar si $page.params.status = FINAL y, a continuación, pase a la página Confirmación de pedido si el resultado es verdadero. Asegúrese de guardar la ruta.
    ![Page Params Final](/images/pageParamsFinal.jpg)
Ya está. Su interfaz gráfica debería tener ahora este aspecto. 
![Graphical Interface Final](/images/graphicalInterfaceFinal.jpg)
También podemos utilizar la herramienta de agente de pruebas. Repase esta conversación con el bot.
![Final Test Agent](/images/finalTestAgent.jpg)

Si su conversación ha funcionado, ¡Felicidades! Acaba de crear un bot de tienda de caramelos.

Si desea ver un vídeo de todos los pasos anteriores, navega hasta este enlace. https://youtu.be/I103nKWivG8 

---
title: "Creando una base de conocimiento"
chapter: false
weight: 40
---

## Creando una base de conocimiento (Knowledge Base)

Ahora que tenemos nuestros archivos HTML alojados en Google Cloud Cloud Storage, ya podemos crear nuestra base de conocimientos en la Consola de Ayuda del Agente de Google Cloud. Siga los siguientes pasos: 

1. Navegue a la consola de Agent Assist y elija su proyecto. https://agentassist.cloud.google.com/projects
2. Haga clic en datos y luego en base de conocimientos y cree una nueva base de conocimientos. Nombre la base de conocimiento con algo descriptivo como "Candy Shop".
![Knowledge Bases](/images/knowledgeBases.jpg)
3. Navegue en su base de conocimiento y luego haga clic en el botón Añadir nuevo para crear un nuevo artículo.
4. Hagamos primero nuestros archivos HTML. Para estos archivos, son de tipo "Sugerencia de artículo" - "Article Suggestion"  y la fuente del archivo es "Almacenamiento en la nube" - "Cloud Storage". Después de elegir Cloud Storage, aquí es donde se pega el URI que copiamos en la sub sección anterior
    - repita este paso para los tres archivos HTML 
    ![Add Knowledge Article](/images/addKnowledgeArticle.jpg)
5. Ahora vamos a cargar nuestro archivo CSV. El archivo CSV es un tipo de conocimiento de "FAQ" y una vez más utilizaremos un tipo de carga de Google Cloud Cloud Storage. Esta vez pegue el URI del archivo CSV que tiene nuestras preguntas frecuentes.

Si quiere ver un vídeo de los pasos anteriores, clic aquí https://youtu.be/WMzIW4j6OYw . 


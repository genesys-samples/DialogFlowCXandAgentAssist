---
title: "Cómo añadir sus artículos de conocimiento a Google Cloud Storage"
chapter: false
weight: 30
---

## ¿Qué son los artículos de conocimiento (Knowledge Articles)?
Los Artículos de Conocimiento en el asistente del agente son en última instancia lo que se mostrará a su agente en tiempo real a medida que progresa una conversación. El contenido de sus artículos de conocimiento puede ser muy variado. Algunos artículos pueden ser descriptivos sobre una pregunta, producto o servicio común. Otros artículos pueden ser un documento paso a paso sobre un proceso que suele confundir a los agentes. Lo bueno de la integración es que estos artículos que vamos a crear aparecerán en la superficie de los agentes sin necesidad de que los busquen. La integración de Agent Assist con Google Cloud transcribirá la llamada en tiempo real y mostrará los artículos relevantes para la conversación. Empecemos.

Algunas notas importantes sobre la carga de los artículos de conocimiento:
1. Hay dos tipos de documentos que se pueden añadir y utilizar para esta integración. 
    - Documentos de conocimiento
    - Preguntas frecuentes
2. Los documentos de conocimiento deben ser archivos HTML 
3. Las preguntas frecuentes (FAQ) deben ser archivos .csv y ajustarse al formato descrito en la documentación de Google Cloud enlazada aquí. https://cloud.google.com/agent-assist/docs/faq#create_a_knowledge_document

## Descargar estos archivos
Navegue hasta este repositorio de github y siga las instrucciones de esa página. A continuación, vuelva a este taller. 
https://github.com/TravisC1720/KnowledgeArticlesForWorkshop 

## Añadir sus artículos de conocimiento a Google Cloud Storage
1. Navegue en su Google Cloud Platform hasta Cloud Storage.
![Cloud Storage](/images/cloudStorage.jpg) 
2. Cree un bucket con un nombre descriptivo. Opcionalmente, también puede crear una estructura de carpetas en el bucket para organizar sus archivos.
![Create Bucket](/images/createBucket.jpg)
3. Suba al bucket los 3 archivos HTML y el archivo CSV que descargó del repositorio de github. 
![Upload Files](/images/uploadFiles.jpg)
4. Copie los URI de todos los documentos de conocimiento en un bloc de notas para consultarlos posteriormente
![Copy URI](/images/copyURI.jpg)

También puede ver un vídeo con los pasos anteriores aquí https://youtu.be/_NIJrpfH68E
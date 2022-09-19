---
title: "Adding Your Knowledge Articles to Google Cloud Cloud Storage"
chapter: false
weight: 30
---

## What are Knowledge Articles
Knowledge Articles in agent assist are ultimately what will be surfaced to your agent in real time as a conversation is progressing. The contents of your knowledge articles can have a wide range of contents. Some articles might be descriptive about a common question, product or service. Other articles might be a step by step document on a process that frequently trips agents up. The beauty of the integration is that these articles that we are about to create will surface to the agents without them needing to search for them. The Agent Assist with Google Cloud Cloud integration will transcribe the call in real time and surface the articles relevant to the conversation. Let's get started.

A few important notes about uploading the knowledge articles:
1. Their are two types of documents that can be added and used for this integration. 
    - Knowledge documents
    - FAQs
2. Knowledge documents must be HTML files 
3. FAQs must be .csv files and match the format described in the Google Cloud documentation linked here. https://cloud.google.com/agent-assist/docs/faq#create_a_knowledge_document

## Download These Files
Navigate to this github repository and follow the directions on that page. Then return back to this workhsop. 
https://github.com/TravisC1720/KnowledgeArticlesForWorkshop 

## Add Your Knowledge Articles to Google Cloud Cloud Storage
1. Navigate in your Google Cloud Cloud Platform to Cloud Storage.
![Cloud Storage](/images/cloudStorage.jpg) 
2. Create a bucket with a descriptive name. Optionally, you can also create a folder structure in the bucket to organize your files.
![Create Bucket](/images/createBucket.jpg)
3. Upload the 3 HTML files and the 1 CSV file that you downloaded from the github repo into the bucket. 
![Upload Files](/images/uploadFiles.jpg)
4. Copy the URI's of all the knowledge documents into a notepad for later reference
![Copy URI](/images/copyURI.jpg)

You can also watch a video of the steps above here https://youtu.be/_NIJrpfH68E
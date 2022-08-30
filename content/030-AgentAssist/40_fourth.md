---
title: "Creating a Knowledge Base"
chapter: false
weight: 40
---

## Creating a Knowledge Base

Now that we have our HTML files hosted in Google Cloud Cloud Storage, now we can create our knowledge base in the Google Cloud Cloud Agent Assist Console. Follow the steps below: 

1. Navigate to the Agent Assist console and choose your project. https://agentassist.cloud.Google Cloud.com/projects 
2. Click on data and then knowledge base and create a new knowledge base. Name the knowledge base something descriptive such as "Candy Shop"
![Knowledge Bases](/images/knowledgeBases.jpg)
3. Navigate into your knowledge base and then click the Add new button to create a new article.
4. Let's do our HTML files first. For these files, they are of type "Article Suggestion" and the file source is "Cloud Storage". After choosing Cloud Storage, this is now where you paste the URI that we copied in the previous sub section
    - repeat this step for all three HTML files 
    ![Add Knowledge Article](/images/addKnowledgeArticle.jpg)
5. Now let's upload our CSV file. The CSV file is a knowledge type of "FAQ" and we will once again use a Google Cloud Cloud Storage upload type. This time paste in the URI of the CSV file that has our FAQ's.

If you want to watch a video of the steps above, click here https://youtu.be/WMzIW4j6OYw . 


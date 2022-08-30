---
title: "Intro to Google Cloud CCAI"
chapter: false
weight: 10
---

CCAI stands for Contact Center Artificial Intelligence and it has three main components; Virtual Agent, Agent Assist, and Insights. Genesys integrates with Virtual Agent and with Agent Assist. Now that does not mean that Insights is not useful if a business is integrating Virtual Agent and Agent Assist with Genesys. We'll get more into that a little bit more down the page. For now, let's talk a bit more in depth about each of these three components. 

## Virtual Agent
Google Cloud CCAI Virtual Agent comes in two forms: Dialogflow CX (advanced), and Dialogflow ES (standard). Both allow you to build lifelike conversational AI bots using Google Cloud's leading AI technology. As you might have inferred from the title of this workshop, we're going to spend the most of our time today on Dialogflow CX. With that being said, let's draw up some of the key differences between Dialogflow CX and Dialogflow ES. 

| Dialogflow CX | Dialogflow ES
| --- | ---
| Advanced Performance Dashboards | Performance Dashboards
| Intuitive visual builder | Form based bot builder
| State of the art BERT based NLU models | Standard high quality NLU models
| Reuse intents and intuitively define transitions and data conditions | Flat data model for simple use cases
| Easily define and detect minor conversation detours | Not supported
| Shared intents and training phrases across flows | Intents and training phrases not shared across sub-agents
| Advanced multi-gurn simulator | Standard simulator
| Biometric voice identification to identify and verify users | Not supported

## Agent Assist 
Google Cloud CCAI Agent Assist provides three key capabilities. 
1. Recommend phrases used by high performing agents to improve the quality and consistency of customer experience
2. Agents can be suggested knowledge base content in regards to a customers issue
3. Transcribes calls in real time for agents to reference during the call or after for analysis

## Insights
CCAI Insights is the one component of Google Cloud CCAI that does not have a prebuilt integration with Genesys Cloud CX. With that being said, there is nothing stopping a customer from using the Genesys Cloud API's to pass interaction data over to Google Cloud CCAI Insights. Insights also is going to be beneficial if a customer is using either the Dialogflow CX or Agent Assist integration because customers can get relevant analtyics data about their Google Cloud resources that they built for those integrations. 
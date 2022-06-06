---
title: "Building a DialogFlow CX Agent"
chapter: false
weight: 30
---
## Terminology
- Agents - Agent is DialogFlow's term for bot. An agent is a natural language understanding module that understands the nuances of human language. You design and build a Dialogflow agent to handle the types of conversations required for your system.
- Flows - Used to define topics and the associated conversational paths. Here's an example of different flows that might be built for a pizza delivery agent.
![Pizza Delivery Flows](/images/PizzaDeliveryFlows.jpg)
- Pages - Pages are configured to collect information from the end user that is relevant for the conversational state represented by the page. See the below example of different pages in blue that might be used for a Food Order flow. 
![Food Order Pages](/images/foodOrderPages.jpg)
- Entity Types and Parameters - If you are familiar with other bot engines, you might know the term slots and slot types. Entity types and parameters are essentially the same. Entity types control how data from end users can be inputted. With entity types, many come predefined such as Number Sequence. Entity types that come predefined are called system entities and entity types that you create are called custom entities. For example, you might create a custom entity type for pizza toppings that only accepts a predefined list of topppings. Parameters capture and reference values that have been supplied by the end user. Each parameter is assigned an entity type. For example, the parameter account number might have an entity type of number sequence. 
- Forms - A form is built for each page and it is a list of parameters that should be collected from the end user for the page.
- Intents - An intent categorizes a users intention based on data called training phrases. Training phrases are example phrases of what end users might type or say that would match up to the intent.
- Fulfillment - Fulfillment enables the virtual agent to respond to the end users question, query for information, or terminate a session. It is possible to call mutiple fulfillments during one turn.
- State Handlers - Used to control the conversation by creating responses for end users and/or by transitioning the current page.

Reference page - https://cloud.google.com/dialogflow/cx/docs/basics 


## Building a DialogFlow CX Agent
Today we're going to build a virtual agent for a candy shop. The candy shop is hoping to use DialogFlow CX to accomplish two items: 1. Allow customers to place orders & 2. Give out store hours. Let's get to work! Try to follow along with either the steps below or watch the video at the bottom of this page.

- Navigate to the Google CCAI Console & ensure that you are in the project that you created in the previous section. 
    - https://dialogflow.cloud.google.com/cx/projects
- If you receive this prompt when you navigate to the link, just enable the API.
![EnableAPI](/images/EnableAPI.jpg)
- Create a new agent and give it a descriptive name like "Candy Shop Bot"
- The first task we will do is edit the Default Welcome Intent. Click on the start button in the middle of the page and then on Default Welcome Intent. Under fulfillment, let's delete the default phrases and add our own; "Thanks for chatting with the candy shop. How can we help you?" Be sure to click save. 
![Candy Shop Hello](/images/candyShopHello.jpg)
- Before we move to the next step, let's go over the Test Agent tool. In the top right, click test agent. If you say hello, you should get back the response we just created!
![Test Agent](/images/testAgent.jpg)
- Now we are going to create a couple of intents and pages. You can create intents two ways; either from the manage tab or inline. We'll show you both ways. Pages can either be created from the build tab or inline. We will first create an intent using the manage tab and a page using the build tab.
    - Select the manage tab > intents > create
    - Name this intent store.hours
    - Enter at least 5 training phrases. Here's two examples.
        - When is your store open? 
        - What are your hours?
        - Be sure to press save after adding your training phrases
    - Navigate back to the build tab and then click the + sign to create a new page named "Hours"
    - Hover over the newly created Hours page and click the 3 dots and then Edit
        - Edit the fulfillment field and then input some text describing your candy shops store hours. For example, "Our shop is open Monday through Saturday from 11am to 9pm."
        - Be sure to press save on both the fulfillment and the page. 
    - Navigate back to the Default Start Flow and then press the Start block
        - Create a new route and choose store.hours from the intent drop down and under the transition section choose the Hours page. 
- Now we are going to create an intent and a page using the inline functionality
    - Click the start block under the Default Start Flow and then the + to add a new route
    - In the intent drop down list click + new Intent, which will allow you to create a new intent directly from here
    ![Inline New Intent](/images/inlineNewIntent.jpg)
        - Name your new intent "Order Candy" and add some training phrases of what a customer might say if they want to order candy. Under training phrases, add the following sentences
            - order some gumdrops
            - place a new order
            - i want candy
            - i want 500 suckers
            - i'd like to buy 10 jawbreakers
        - You should notice that a parameter is automatically created when putting in your training phrases. Google is recognizing based on your inputted training phrases that you are going to need to gather the quantity of candies as a parameter for this intent. We'll get more into adding parameters here in just a little bit.
        ![Parameter Autopopulate](/images/parameterAutopopulate.jpg)
    - While still editing the route, navigate down to the transition section and now let's create a new page using inline functionality. 
    ![Inline New Page](/images/inlineNewPage.jpg)
        - name this page "New Order" and then save your route
- Quick check in - at this point, your graphical editor should look like this. 
![Graphical Editor Check In](/images/graphicalEditorCheckIn.jpg)
- Next we need to add parameters to our New Order page...

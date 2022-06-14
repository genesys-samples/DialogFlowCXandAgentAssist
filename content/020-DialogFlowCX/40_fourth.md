---
title: "Invoking the DialogFlow CX Agent in an Architect Flow"
chapter: false
weight: 40
---

## Invoking the DialogFlow CX Agent in an Architect Flow
We're on to the final step. Now that the DialogFlow CX Agent is complete, we can now call it in an architect flow. This will truly complete our end to end integration from Google to Genesys with all the capabilities of Google DialogFlow CX and Genesys Cloud CX Architect available for our candy shop. We're going to make this rather simple for today's purposes. Please follow along. 

- Open up Architect in your Genesys Cloud CX application and navigate to create a new message flow. Give it a descriptive name and click create. 
![Create Message Flow](/images/createMessageFlow.jpg)
- In the intial state block, drag a "Call DialogFlow CX Bot" Block into the beginning of the state. From the drop down list, choose the Agent that we just created.
![DialogFlowCX Architect Block](/images/dialogFlowCXArchitectBlock.jpg)
- Now we will get the parameter data from the DialogFlow CX session. 
    - In the same block, under session parameters, add two outputs. Name the ouputs Candy and Quantity since those were the parameter names we created on the Google side. Assign those parameters variable names that way we can leverage them in our architect flow.
    ![Architect Parameters](/images/architectParameters.jpg)
- At this point, we realize that we want to add an option for a customer to talk to a live human. Let's go back into the DialogFlow CX agent that we created before and add a new route from the start block. 
    - Using the inline functionality we learned about before, create a new intent named LiveAgent with some training phrases that are applicable. 
    ![Live Agent Intent](/images/liveAgentIntent.jpg)
    - While still working within that route add a new dialogue option under fulfillment. Choose "live agent handoff" as the type and then add this text to the body.
        - {
"Intent": "LiveAgent"
}
![Live Agent Handoff](/images/liveAgentHandoff.jpg)
    - While still editing that route, make the transition to a new page and set that page as End Session. End session will allow us to exit the DialogFlow CX agent and pass back to architect.
    ![End Session](/images/endSession.jpg)
- Navigate back to architect (you may need to press save and then refresh the screen since we just made changes to our DialogFlow CX Agent) 
    - Back in your Dialogflow CX bot block, add some output under the Live Agent Handoff Metadata section. The key name should match the key name that we created in the previous step. For variable name, set a name to be referenced from within Architect. 
    ![Architect Live Agent Handoff](/images/architectLiveAgentHandoff.jpg)
    - Under the success route in architect, drag a decision block and let's make a decision on if our variable for intent equals LiveAgent (hint: if you named your intent something different in Google, you'll need to try to match that name in Architect)
    ![Intent Decision](/images/intentDecision.jpg)
    - If this decision evaluates to yes, then transfer to a queue that you are a member of. Lastly, add a disconnect to the bottom of the flow and then publish!
    ![Final Architect Flow](/images/finalArchitectFlow.jpg)
    - Now let's test this! You'll need to create a web messenger configuration and deployment. That isn't the lesson of today's workshop so if you don't already have this set up in your org follow the instructions below. 
        - Configuration - https://help.mypurecloud.com/articles/configure-messenger/ 
        - Deployment - https://help.mypurecloud.com/articles/deploy-messenger/
    - Last step! Navigate to our web messenger developer tools in the developer center and choose your deployment you created. https://developer.genesys.cloud/devapps/web-chat-messenger 
    ![Web Messaging Tool](/images/webMessagingTool.jpg)
    - Go through this conversation. 
        - You: "Hello!"
        - Bot: "Thanks for chatting with the candy shop. How can we help you?"
        - You: "Order candy"
        - Bot: "What type of candy do you want to order?"
        - You: Choose any candy type you want here
        - Bot: "How many *candy type* would you like?
        - You: Put any number here
        - Bot: "We’ll have your order for *quantity* *candy type* ready in two business days!"
        - You: "When are your hours?" 
        - Bot: "Our shop is open Monday through Saturday from 11am to 9pm."
        - You: "Talk to an agent"
    - This will then send the interaction back to architect and route to our queue! You should then be able to handle the interaction from the interaction pane by going on queue and accepting the interaction. 

You can also watch a video of these steps here https://youtu.be/AoCeX5RjT0Y

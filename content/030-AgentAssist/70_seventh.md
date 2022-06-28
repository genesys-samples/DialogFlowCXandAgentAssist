---
title: "Creating your Agent Assistant in Genesys Cloud CX"
chapter: false
weight: 70
---

## Creating your Agent Assistant in Genesys Cloud CX
1. Navigate to your Genesys Cloud CX admin console. The first step we need to take is to be sure that our user has the correct permissions to add Agent Assistants. Either create a new role or edit an exsisting role with the following permissions. Once you have the role, add it to your user.
    - Assistants > Assistant > Add
    - Assistants > Assistant > Edit
    - Assistants > Assistant > View
    - Assistants > Queue > Add
    - Assistants > Queue > Edit
    - Assistants > Queue > View
    - Assistants > Queue > Delete
    - Telephony > Plugin > All permission
2. You may need to refresh your screen after giving your user the permissions, but you now should have an Assistant button under Contact Center in the admin page that wasn't there before. Click on the Assistant option.
![Assistants Admin](/images/assistantsAdmin.jpg)
3. Click to add a new assistant. Give the Assistant the name of "Candy Shop" and paste the conversation profile integration ID that we had copied in a previous step. Press save. 
![New Assistant](/images/newAssistant.jpg)
4. Once you press save, a new tab will appear up top for you to assign this assistant to queues. Assign this assistant to a queue that your user is apart of that way we can test what we have built.
![Assign to Queues](/images/assignToQueues.jpg)

## Testing the Agent Assistant
We're finally at the last step, where we get to see the integration in action!
1. There are a few prerequisites that you need to be able to test agent assist. Those are: 
    - Your user is a part of a queue (the same queue that has the Assistant assigned to it)
        - https://help.mypurecloud.com/articles/create-queue/ 
    - Your user has the proper permissions to handle a voice interaction and a phone assigned to them   
        - The "Genesys Cloud User" (May also be called PureCloud User) should give you the proper permissions
        - https://help.mypurecloud.com/articles/configure-the-genesys-cloud-webrtc-phone/ 
            - hint: your org may already have base settings created
    - You have an architect flow that transfer to the queue that you are assigned to
        - https://help.mypurecloud.com/articles/create-call-flow/
    - You have a call route set up that connects a phone number to the architect flow that transfers to your queue
        - https://help.mypurecloud.com/articles/add-a-call-route/
2. Now it is time to put on your agent hat and test the assistant we just created. First navigate to the Interactions pane and then go "On Queue"
![On Queue](/images/onQueue.jpg)
3. Call the number assigned to the call route that connects to your architect flow and gets the call to transfer to your queue. Accept the interaction. 
    - Hint: You might want to mute the agent leg. The close proximity of both the speakers from your cell phone and your webRTC phone can cause an echo. 
    ![Mute](/images/mute.jpg)
4. Click on the Assistant call control and then open up the transcription section as well.
![Assistant Call Control](/images/assistantCallControl.jpg)
5. On the phone that you are calling from ask the following questions and confirm that Agent Assist is sufarcing the correct articles or FAQs. Also help train the Assistant by marking the articles/FAQ's either relevant or irrelevant as they surface.
    - Let's start with the FAQ's. As the customer, ask the following: 
        - "When is your store open?" 
        - "Do you offer vegan candy?" 
        - "What is your most popular candy?" 
    - Now to the knowledge articles (these you will click the link and it'll open another tab)
        - "I want to check my delivery status"
        - "I need to file a complaint"
        - "I have a special order"
        ![Mark Relevant](/images/markRelevant.jpg)

If you want to watch a video of the steps in this section navigate here. https://youtu.be/7pw1l1o8om4
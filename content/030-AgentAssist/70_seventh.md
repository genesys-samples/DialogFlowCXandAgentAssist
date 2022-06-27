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
We're finally at the last step, where we get to see the integration in action!...
1. 

If you want to watch a video of the steps in this section navigate here... 

### Intro 

Flows are the most basic drag and drop tool available and is an administrator skill . Salesforce expanded the functionality of flows rapidly as they were easy to customise . Flows are pretty straight forward , they provide easy error logging and debugging mechanisms . Based on requirement there are multiple flows available at the admin’s disposal to build . 


### Screen Flows 

- Screen Flows are the sort of flows that are presented to the user , they are available for user interaction . 
- They can be used almost everywhere  , on FlexiPages , actions , list view etc . There is a way to even have them populate on LWCs therefore their use case is very vast . 

### Autolaunched Flows 

- These flows are run upon invoking , they have to manually called every time instead of invoking upon automation . 
- Their use case is that they can be called through code , API  and can even be used as subflows . 

### Record Triggered Flows 

- Record triggered flows are exactly as the name suggests , they work exactly like triggers , they have before and after save , before and after create , and before delete as well . 
- Record Trigger flows can cause flow recursion something a developer should be mindful of to avoid computational wastage . 
- Update Record elements should never be in a loop , they should instead be added to the record collection variable and updated once the loop is completed . 
- Before Save Flow on the other hand does not require update records element to update the new and old record collection  . Assignment element can instead be used for such use cases to directly manipulate the records . 
- Before and After save elements are usually segregated for the performance optimisation function they have to offer . Before Save are used more for fast field updates whereas after save are used for more time consuming purposes such as updating related records or sending emails . 
- Before Save flows can also be used to add validations . 

### Scheduled Trigger Flows 

- These flows are simple and a drag and drop version of batch classes . They are just used for clean-up purposes . 

### Platform - Event Trigger Flows 

- As the name suggests these flows are invoked upon the firing of platform events. 

### Orchestrated Flows (Record-Triggered and Autolaunched Flows )

At times in a business , we are often required to follow a certain procedure for certain type of requirements . Such as having a regular troubleshooting process for a case or let’s say HR team having a specific process that can be used to streamline their recruitment process etc. All of these scenarios have a few things in common . 

- Stages - Each process has a stage and this stage is a combination of multiple task/step in required sequential order . 
- Step- Each step is a part of a stage . Each step is usually a flow . If the step is interactive , it would be a screen flow or else an autolaunched flow . 
- Work-item - Upon the offset of each step , a work item is created and assigned to a user/queue to be worked upon . 



### Approval Process 







Literature : [[Tell me everything you know about screen flows]] , [[What are all the types of Flows in Salesforce]] , [[Orchestrate Complex Processes with Flow Orchestration]] , 
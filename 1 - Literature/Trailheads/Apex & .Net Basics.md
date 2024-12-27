
#### Map .Net Concepts to the Lightning Platform
- Apex is a java based language but has similarities much more to that of C# . 
- Apex is an Object-Oriented Programming Language and supports all primitive data types and apex has a couple of other primitive data types such as ID(18 character alpha-numeric string) and sObject.
- Visualforce is render webpages and it is somewhat similar to ASP.net . Visualforce follows an MVC Structure and Since HTTP is stateless visualforce pages are stateless as well ( need to use controllers ) .
- Apex does not support arrays , at least not directly . `List<dataType>` has to be initialised to store data in the for of a collection . 


#### Understand Execution Context 

- In the salesforce ecosystem , execution context is the start of the time of execution of a piece of code . 
- Whenever a piece of code is fired the execution logs notify saying "Code_UNIT_STARTED"
- Whenever a piece of code is fired a fresh set of governor limits are issued and for the entire subsequent transactions that are tied to the parent transaction , the governor limits are followed and not updated . Even the governor limits are mentioned within the execution log . 


#### Use Asynchronous Apex

- Use Future methods for the below three
  - Web callouts 
  - Bulk record processing 
  - Offloading computation for better user experience . 

- Limitations with future calls is that they are not trackable , and they cannot be chained which means that one future method cannot be called inside another . 
- Future methods have to be Static , return void , and can accept only primitive data types as parameters . 
- Batchable is a special kind of asynchronous action which lets developers to perform operation on records as large as millions and let them to track the execution of the job . 
- Queueable is another asynchronous action that brings the best of both world from Future actions and batchable . 
  - It lets developers use non-primitive types as parameters . 
  - It allows developers to chain other asynchronous actions . 
  - It also lets devlopers to monitor the the through JOB Id . 


#### Debug and Run Diagnostics 

- To debug code , we can setup standard logs using `System.debug('Debug Message)` . 
- There are multiple levels upto which we can setup logs , each level increasing the verbosity of the debug log and painting a crystal clear picture . 
- The limit of each debug log is 20MB(quite a lot) . And The org can retain up to 1000 MB of debug logs . 
- Similar to JS and C# , apex has Checkpoints , much different from Breakpoints . Since Salesforce is has a  cloud based multi-tenant architecture , stopping the execution would impact other organisations. 
- Checkpoints do the same as breakpoint , they give the necessary details to debug . they just don't stop the execution . That's it . 
- 


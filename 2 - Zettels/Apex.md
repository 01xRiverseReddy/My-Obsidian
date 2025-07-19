
### Background 

Apex is an object oriented language that is much similar to Java and is strongly typed . What strongly typed means is that the type of the variable is checked during compile time unlike javascript that is checked during runtime . 
Apex is cloud stored and compiled language , which means that there is no way to run apex locally . 
Apex is solely used to run business logic on salesforce platform . 


### Variables 
- The variables offered in Salesforce are the regular standard ones that we would ordinarily find in a programming language . 
- A special kind of variable is an `sObject `  , which a generic data type to store the records in salesforce . 
- When a variable is initialised and not assigned in salesforce its value is a null value . Therefore if a Boolean value is initialised and not declared , it would not default to false . 

### Data Structures 

- The apex language offers the same regular data structure as java . 
- Hashmap , set , dynamic array etc are the regulars . 
- In this languages these three are most commonly used data structures . 


### Tight coupling with Database 

- The huge benefit that apex offers is that it is very tightly coupled with the apex programming language . It makes it very easy for the apex language to interact with database and perform modifications . 
- The coupling is seamless and completely black boxed to the end developer . 
- SOQL and DML statements are the methods used to interact with the database . 



### Governor Limits and Multi-tenant Architecture 

- Salesforce is multi-tenant architecture which means that the resources that the salesforce cloud allocates has to be equally divided amongst the subscribers of salesforce( based on the level of subscription ) . 
- Governor Limits are a perfect way to ensure that no particular entity or organisation used the complete computation block on the cloud . 
- There are certain limits such as having 100 SOQL queries max , 150 DML statements max per transaction . 6Mb heap memory per transaction . 


### Asynchronous Processing 

- Apex is also designed to offer asynchronous computation that most modern programming language leverage . 
- One of the ways it provides is through batch jobs where when a whole lot of processing is needed on a whole lot of records . Batch Job is the same as CRON Job . It is scheduled and processed asynchronously , the benefit being is that it is way faster and better . 
- Asynchronous processing has increased governor limits such Heap size is 12 mb , future calls are allowed up to 50 . 





### Literature 
[[Apex & .Net Basics]]
[[Apex Basics & Database]]
[[What is Apex and How is it used in Salesforce ?]]
[[Explain the structure of Apex Programming Language]]
[[What are some special things about apex ?]]
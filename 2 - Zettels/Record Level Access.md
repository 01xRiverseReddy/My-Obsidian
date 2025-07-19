
### Intro 
Record level access in salesforce can be subdivided in to four categories and these four categories are hierarchically structured .

### Org Wide Default Settings 

- Org Wide Defaults settings are options limited from ‘Private’ , ‘Public-Read Only’ , ‘Public Read/Write’ . 
- Org wide defaults are by default set ‘Public Read/Write’ which means that anybody who has access to the record can read and edit . 
- ‘Private’ Means that only the user that owns the record will be able to see the record . 
- ‘Public-Read Only’ gives access everyone who has access to the record to only read the record restring the record edit access . 


### Role Based hierarchy 

- This level of access is only applicable if the org-wide default setting are either set to ‘Private’ or ‘Public Read only . 
- Role based hierarchy is basically defines that any record level access that a certain user with a certain role owns can be transfer the Same level of access to the roles higher to that . 


### Sharing Rules 

- Sharing rules are also applicable only when org-wide default settings are either ‘Private’ or ‘Public Read only’ 

- Sharing rules are automatic exceptions that are set to override Org Wide Defaults Settings and Role Based hierarchy . 
- It is basically a rule that is written with a certain criteria and if the criteria is fulfilled either ‘Read’ or ‘Read/write’ is assigned based on the set configuration . 


### Manual Sharing 

- Manual Sharing is when the owner of the record willingly provides rights to a certain user . 
- This can be useful if a user intends to transfer his work before heading to a vacation . 




Literature : [[Data Security]]
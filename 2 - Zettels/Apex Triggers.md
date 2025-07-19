
### Intro 

Apex triggers are similar to triggers in SQL , much like whenever a row is modified we can write logic in the triggers to execute any custom background operation to satisfy business needs . 
Apex makes it extremely friendly and easy to tie up the database and apex code making it easy to perform simultaneous . 


### Context variables 

Trigger Context Variables provide the context of the current invoked trigger . The trigger variables that are available for disposal are mentioned in the literature section of this Zettel . 

One of the trigger variables that is not mentioned in the literature tabs is “is executing” and returns true if the apex code’s context is a trigger rather than a visualforce page , web service or an executeanonymous() API call . 



### Before Save 

- This Trigger is mainly used for field updates . It makes updates on fields very fast and is one of the recommended practices . 
- Add Error method available in Before save of the trigger is really helpful in performing complex validations . For basic and simple necessities validation rule is ideal , but when related records or other variables become part of the equation this is perfect. 

### After Save 

- This trigger is primarily used for updating related records or sending out email . It is recommended according to best practices that all computationally intensive operations be performed in the after save trigger . This includes making API callouts as well . 



### After Delete 

- This trigger is mainly used for cleanup purposes , such as removing related records on updating related records etc . 
- 


Literature : [[What are all the trigger context variables available in Apex Triggers]]
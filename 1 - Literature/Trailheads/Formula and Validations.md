
#### Use Formula Fields 

- The purpose of formula fields is to increase customer productivity , by automatically calculates certain things that the customer regularly does . Ex Day left for an opportunity to expire . 
- Formula editor is pretty simple , it is self explanatory for the most part . It is a click and point tool that does not need coding . 
- A formula field can only be saved if it is free from errors . 


#### Implement Roll - Up Summary Fields 

- Roll up summary fields are a special type of formula fields that are used to calculate the aggregate of the related records . 
- This can only be implemented when the related records have a master-detail relationship . Which means that the Object has to be the master for the field to be implemented on . 
- Key limitations of these fields is that it cannot reference formulas fields that have cross object relationship. Meaning that if the detail object is has a formula field that is referencing a field on another object for relation , that formula field cannot be used to aggregate in the roll-up summary . 
- The key thing to try out is . What if there are two formula fields where one is a cross-object formula field but the other is just referencing this formula field . Can the same object formula field be used to aggregate ???


#### Create Validation Rules

- Validation rules are a special kind of formulas , that can only return a boolean value . 
- Validation rules's primary use case is to safe guard faulty records . 
- Before Records are saved/created , validation rules ( written in formulas ) will fire to check if the record that is being updated has a valid or not . 
- Validation rule will show on error message either on the field or at the bottom of the record page (depending on dev choice ) if the rule fires and return the value "True" . 
- 

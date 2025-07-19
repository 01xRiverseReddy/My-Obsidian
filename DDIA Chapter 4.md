
### Encoding 

- Encoding is nothing but representing application layer data which is in the form of Arrays , Trees , Hashmaps , or mainly Object to a multi-operable data format which is primarily JSON or XML . 
- The process of encoding brings in minor issues such 
	- Backward and forward compatibility . The data that is encoded today might be differently encoded in a decade .
	- Data that is encoded in Java might be a little different as to how it would be encoded in python introducing integration incompatibility . 
	- Encoding and decoding definitely takes time converting it to JSON or XML 
- JSON and XML are the most widely used industry standard encoding formats . Apart from these two binary representation caught up some form of attention as it is faster by a small margin when operating with regular sized data sizes but make a significant different when the data sizes emerge in terabytes . 
- XML and JSON usually operate on a schema-read or Schemaless manner offloading all the validation on the application layer’s side . The problem with this that any new changes will require and application code update . 
- Binary encoding somewhat looks like this 
- ![[Pasted image 20250501123430.png]]



### Thrift and Protocol Buffers 

- These are binary encoding libraries that are developed by Google and Facebook . These are semantically the same thing when compared to the previous screen . 
- They have a schema , IDL interface definition language , that’s they use to encode and decode . This IDL is compiles and a class is generated that used to encode and decode data in the mentioned Schema . 
- These protocol buffers operate smartly and reduce the no of bytes that are needed to encode by making the key values compact , restricting it to only two bytes . (For better understanding this can be referred to as the API name like in salesforce ). These two bytes are then decoded to actual key values while deserialization . 
- These libraries are cool and all but they come with problems 
	- The code generation from schema is fine when used with static type checking languages but not with dynamic type checking languages due to ambiguity . 
	- Schema evolution is somewhat tricky when considering backward compatibility . Usually when adding a new required field or something . 

### Avro 

- Avro works differently from Thrift and Protocol buffers , it does not encode field names at all and goes with a different approach . 
- There is a writer’s schema and a reader’s schema . Writer’s schema to encode and reader’s schema to decode . 


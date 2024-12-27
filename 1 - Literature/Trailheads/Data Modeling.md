
#### Optimise Customer Data with Standard and Custom Objects

- Salesforce offers customers to store their data in the form of Objects .  In the outside world data as often represented as rows and columns in a table (SQL) . 
- Tables are what are known as Objects in salesforce . Objects can be Standard Objects or Custom Objects . 
- Standard Objects include Accounts , Contacts , Opportunities  etc the ones which are used by every organisation no matter who. 
- To build our own functionality salesforce offers something such custom Objects , kind of like building our own table and adding our own columns .
- In Salesforce , columns are referred to as fields . There are 4 kinds of fields :
  - Identity - This is ID field and it is unique 
  - System - These are read only fields , created date , last modified date 
  - Name - This a special field this used to identify records . It can be either an auto - number (immutable) or text field (mutable ) . 
  - Custom - Created by users for our custom need . 


#### Create Object Relationships

- Object Relationships are a functionality that can be established in salesforce with custom fields . It can be better explained as JOIN operation in SQL . 
- For instance and Object relationship can look like this . One Account and multiple Contacts underneath . Here Account object and the Contacts are related . 
- There are two types of Object Relationships  - Lookup and Master-Detail .
- Lookup Relationships are fairly simple , we can just establish a one-to-one or a one-to-many relationship between any two objects . 
- Master-detail relationships are much strict . Master-detail are one-to-many and whenever the master record is deleted , the detail is deleted along with it . 
- Hierarchial relationships are a special kind of relationships available only to the user object . This is to establish a heirarchy like VP -> Manager - > Subordinate 


#### Schema Builder

- Schema builder is a tool from setup to view the relationships between object in a pictorial manner . 
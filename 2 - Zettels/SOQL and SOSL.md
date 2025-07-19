
### SOQL 

SOQL stands for Salesforce Object query language  .  SOQL is much similar to SQL in terms of how data is structured and related . Accessing relational data in SOQL is done through relations rather than joins . 
#### Syntax

```
Select [FIELDS COMMA SEPERATED] from [ObjectAPI name] where [FILTER CRITERIA]
```

Unlike SQL , SOQL does not offer UPDATE , INSERT OR DELETE all these operations are done through code via DML operations 

**Aggregate functions** Aggregate functions are some thing that return an attribute of the query such as COUTN() MAX() MIN() AVG() . 

**Child to Parent**
```
SELECT Name, Account.Name FROM Contact
```

Parent to Child 
```
SELECT Name, (SELECT LastName FROM Contacts) FROM Account
```

#### Key Features of SOQL:
- **Filtering with**  WHERE, AND, OR, IN, LIKE, LIMIT, etc.
- **Aggregation** : COUNT(), AVG(), SUM(), MAX(), MIN() (though limited).
- **Ordering**: ORDER BY Name ASC
- **Pagination** : Use OFFSET and LIMIT.
- **Date functions** : e.g., WHERE CreatedDate = LAST_N_DAYS:30
- **FOR clauses** : FOR UPDATE, FOR VIEW, FOR REFERENCE

### For clauses 
For clauses are something that are used for pinpoint precision in using the query . They are usually mentioned for the utility / use case . 
- For Update - this clause should be used when the query is retrieved is used for update operation . This should be used very carefully as this clause locks the record ( to protect against race conditions )  if not used properly  can lead to deadlock scenarios . 
- For view - This is used when the query retrieved is used to render on page or to update tracking of the ‘lastviewed’ property . 
- For Reference - This is used when we don’t want the query to update the lastvieweddate property . 





### SOSL 

SOSL stands for salesforce object search language . The main idea behind SOSL is to build a custom search query for specific use cases where SOQL does not entirely fulfill the requirement 

#### Syntax 
```
Find ‘SearchQuery’ [IN SearchGroup] [Returning ObjectAndFields]
```

The search query mussed be enclosed within Single Quotes if it is just one word . Double quotes for phrases or multiple words . 

Search Group is optional , by default it is all fields . The options however are limited from ALL FIELDS , NAME FIELDS , EMAIL FIELDS , PHONE FIELDS , SIDEBAR FIELDS . 

 Objects and fields are used to return the Objects and Fields that the search query is relevant to . By default it would be all objects and fields , which is something we would not want to do . 

When used in apex the return type is `list<list<sObject>> `  . 

### Key considerations for SOSL 

1. The governor limit for SOQL is 2000 rows / records . 
2. SOSL performs better than SOQL in large text searches and SOSL searches only on indexed fields 
3. SOSL enforces User-fields level security as well Object level Security .
4. Wildcard operator `*` is expensive in SOQL and should be rarely used . 
5. SOSL is susceptible to injection attacks so any dynamic or user provided text has to be parsed with sanitisation functions . 

  







Literature : [[SOSL Sanjay Gupta]] [[Search Solution Basics]]  [[What is SOQL is apex and what are somethings I should keep in mind]] [[What is SOQL and how does it work in Salesforce]] [[What are FOR clauses in SQL and how are they used]]
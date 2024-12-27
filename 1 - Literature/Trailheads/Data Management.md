
#### Import Data 

- The best way to store data is in the form of CSVs . 
- There are two tools to import Data into salesforce 
  - Data Import Wizard
  - Data Loader
- Data Import Wizard is a functionality provided by salesforce . It is recommended that this should be the got option. But there are a few shortcomings for this functionality -
  - It can import up to 50k records only 
  - It cannot support opportunities 
- Data loader is a better option when -
  - importing 50k to 150 million records 
  - Scheduling regular data loads .
  - Some objects are not supported by Data import Wizard  . 
- Multi-select picklist fields need to have values seperated by semi-colon to be imported . 
- Date / Time fields need to be in the supported format . 


#### Export Data 
- You can directly export data using two options 
  - Data Export Service 
  - Data Loader
- Exports can be scheduled in intervals , 7 or 29 days . 

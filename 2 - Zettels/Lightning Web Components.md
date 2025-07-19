
### Intro 
Lightning Web Components is a front-end web framework developed by salesforce , for developer to extend the component based approach and build dynamic personal scenario based UI . In in LWCs , each component has three main files - HTML , JS , XML .


### HTML 
- The HTML file is where all the rendering happens. All the HTML in the file is supposed to be enclosed within one Template tag. 
- The HTML is tightly binded with the variables in the javascript . The variables in javascript file can easily be referenced in the HTML file after rendering . 
- Salesforce offers a bunch of pre-built components for generic use-cases following Salesforce’s UI which can easily be copied to the HTML file by referencing the documentation . 


### JS

- The JS file is where all the client-side logic processing happens . The class is initialised by `export default class class-name extends LightningElement ` and here lightningElement is an interface . 

### Meta-XML 

- Meta-xml file is the file where we decide on the different pages where we expose the LWC component . This can be on Lightning Home page , Record Page , etc . 
- The input parameter for the LWCs Meta-xml file have to be assigned from the meta-xml file . 



### Decorators 

#### API 
- API decorator is annotated with @api and it used to make a variable/property in a javascript file public . By public it means that the variable is not only confined to the class, call it can be referenced in the parent component .
- Any form of data that is passed through the metadata has to eventually flow into an api variable . 

#### Track
- Track decorator is to mainly enable tracking on the variables in the javascript file so that they can be dynamically rendered on the HTML page . After winter 20 release all variables are by default tracked . 
- Track Decorator is useful in cares of Objects and arrays as object and array re-renders when the reference to them changes . Not when the individual attribute is mutated . *More in literature*

#### Wire 

- Wire decorator is used to wire data from the salesforce database to the client-side property . It is basically an apex method that is invoked in the lwc to get records . The method is usually the followed by a chained method to process the result . 
- The apex method has to have cacheable set to true . Which means that it is not good to have dynamic data retrieved in the wire method . 



### Parent-Child Communication 

- Parent to child communication happens directly to passing down properties as attributes to the HTML component . This can be done through setting the property up with an api decorator . 



### Child-Parent Communication 

- Child to parent communication happens via events . When necessary the child dispatches an event and the event is detected on the parent component level and the the values/properties are referenced in the parent component from the detail attribute of the event.  






### Literature 

[[What is the significance of track decorator ?]]





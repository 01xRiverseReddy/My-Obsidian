
### Introduction
- In the modern day world computing power is not the limiting factor to build big applications , it is how well we manage the huge influx of data that these applications receive . 
- Data systems are put in place to manage this and there different types such as databases , caches and search index and even for these there are sub-types to suit each use case . 
- Big applications have their system broken up into multiple tools where each tool specialises in a task . When you have several of these tools working together and have them exposed as a service for external or internal use , you have essentially built an API . ![[Pasted image 20250126103715.png]]


### Reliability 

- Reliability is one of the three main characteristics of a data system . Reliability of a data system describes how low it is susceptible to downtime . Downtime is usually caused by fault and failures . Fault is any unexpected behaviour that deviates from the main flow of the data system , where is failure is an event that results in the complete downtime of a data system . (Chaos Monkey).
- Netflix’s Chaos Monkey is a tool that generates random faults within the system to test the resilience of a system . 
- The three main types of failures are Hardware errors , Software errors , Human errors . 
- #### Hardware errors
- Hardware errors could mainly be something like disk failures , or memory corruption etc . Even in present day scenarios redundancy is one of the most used solutions for disk failures , where a disk is replaced/backed up with another disk when it is approaching closer to its mean time to failure (MTTF) .  
- #### Software errors
- Software errors - Software errors are the type that happen on the codebase level , this can be something as simple as not handling edge cases . 
- #### Human errors 
- Human errors are the most commonly occurring errors compared to the previous , this is mainly caused due configuration mistakes , people being careless etc . 



### Scalability 

- Scalability is the next main characteristic of data systems which describes that as load increases on the system , will the system remain consistent with its performance . 
- Load can be described through load parameters which can be requests per second , read/write ratios , cache hit frequency etc. 
- #### Twitter Case Study 
- Twitter had two main use cases , one where the user tweeted and the other where he requested his own home page( shows all the tweets of the people he followed ) . 
- The main Problem was not with tweeting alone but with requesting the home page . Requesting the home page had to join some tables which were expensive and query from a huge database of tweets . 
- To solve this problem twitter created a cache system for each user and what would happen is whenever a user tweeted the tweet would to the cache system of each follower (much similar to a mail system ) and then when users query would become faster as he does not have to query the entire home-page . 
- In the modern day , twitter uses a hybrid of both these things because some of the users have 30 million followers which means for a single tweet they would have to hit the cache of 30 million users . ![[Pasted image 20250127172818.png]]


- #### Load
- After setting a clear definition of what kind of load is received or how much it is received , load , performance is the next factor that is measured in scalability. 

- #### Performance
- Performance too has parameters I am guessing , but response time is one of them . 
- One way of measuring response time is using it average response time . It is literally the response time of n request summed up and divided by n . 
- This is a flawed metric for the reason being is that it does not tell us how many users are experiencing increased delays. 
- Another metric to measure response time is percentiles , percentile is nothing but if we sort the entries array of response times and we pick the exact middle index to be considered as the metric or standard for response time . Then the percentile would be 50 .  If 50% percentile is 1.5s , it means that more than half the user are getting responses faster than 1.5s vice versa . Amazon uses high percentile for its internal services response times as it found a direct correlation between that and sales . But after a point it stopped optimising the response time as it realised that it was counter productive . 
- queueing delays account for major slow response times , where as low as to one to a few slow request stack up the cost of entire packet speed . This is know as tail latency amplification . 
- The approach to scale load is in two ways , either vertically or horizontally . Vertical scaling is when we build a larger and more powerful machine to accommodate the load , whereas horizontal scaling is adding more smaller and cheaper machines to divide the load and cope with it .
- For systems which highly irregular load , the vertical system which are elastic is a good option. An elastic machine would add more computational power and drop it as well totally depending on the depth of the load . 


### Maintainability
- Maintainability refers to keep the state of the system in a working condition . This could include fixing bugs , adding enhancement , clearing technical debt . 
- The maintenance has 3 principles which determine how well a software is maintained and sets a standard as to how a system should be designed  . 
- ##### Operability 
- Operability refers to how easy a software can be worked on . An easily operable system will have less limitation and can easily be worked around with smart operations .
- An operation team would ideally work to keep the software running smoothly , this could involve finding bugs , implementing security patches , anticipating future faults . 
- #### Simplicity 
- Simplicity refers to how easy it is to build up on existing projects . Initial stages of development and small scale companies will usually have small codebases will have easily readable code not much abstractions and hence would be simple . 
- As time progresses and companies scale the complexity of the systems and the codebases complicates and often leaves developers stranded to puzzled logic . 
- Abstraction in the tech world is an amazing technique that can be used to mask the complexity and make it easier for engineers to build upon existing systems . 
- #### Evolvability
- Evolvability  is. ,in my opinion at least , the hardest and the most important thing to consider when building a system . In the ever changing space of technology the combinations in which future technology could branch into is incalculable . Evolvability is the factor that considers how it is for a system to progress with technology .
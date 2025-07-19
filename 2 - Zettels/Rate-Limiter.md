#SystemDesgin 

###  Intro

Rate-Limiting is technique and rate-limiter is an implementation of this technique to limit the requests a client makes mainly because to optimise resource allocation and priority requests . Most applications use third-party APIs which make it necessary to limit the requests that come in . 


A Rate limiter can be on the client side or the server-side . Client side rate-limiter is practically useless as it can be easily bypassed . Server-side implementation is more practical depending on the tech stack and the programming language . Due to priorities or whatever is going internally the engineering team can offload rate-limiting to API gateways which might already be handling authentication and other things . In this case the engineers would have to give up some flexibility as they do not have entire control over the application .




### Rate Limiting Algorithms 

I will have to revisit this because I am not focused 



### High Level Architecture 

- Rate-limiting Systems have Rate-limiting rules in place , which is the criteria that is evaluated for each type of request 
- Rate-limiting headers in the HTTP response contain details regarding the limits set such as requests remaining , the limit until next request etc 
![[Pasted image 20250512115017.png]]

- Race Conditions : Rate-limiting software face race condition issues where two request read the same current limit update the same value . 
- Synchronisation : This issue occurs when one client making one call to one rate-limiting software proceeds to make the next to another rate-limiting software of the same application . This can be mitigated by having on Reddis server that all rate-limiting servers make call-outs to . 
- While monitoring , cache rules and rate-limiting algorithm need to be in mind . String cache rules might drop valid requests and poor rate-limiting algorithms degrade application performance . 
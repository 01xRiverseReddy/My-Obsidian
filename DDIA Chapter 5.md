

### Replication 
- Replication basically means to have copies of your data stored in multiple instances in case the main instance fails and we can still keep our data systems resilient . 
- There are multiple techniques to add resilience to our data systems . The approaches are single-leader , multiple-leader , leaderless architecture . 
- Single-leader is perhaps the most famous often know as master slave architecture with one master solely used for writes while the slaves only for the reads . 

### Synchronous and Asynchronous replication 

- Synchronous replication is when the master registers the writes and publishes the writes to slaves . The master confirms the writes only when the slaves have confirmed the writes as well . 
- This introduces problems as there could be a delay at one the slaves which directly introduces a latency issue . 
- The slave node in worst can completely break down and never send a response .
- Asynchronous replication on the other hand is different . The writes are registered to the master and the master instantly confirms the transaction synchronously publishing the writes to the slaves . 
- While this may look fast and a solution to latency issues in synchronous . This also introduces a problem . If there writes are not registered with slaves and the read happen on slaves then data will eventually get corrupted . 


### Setting up new slaves and Failovers 

- Setting up new slaves is done by copying a snapshot of the master database and pulling the changes that have happened form the moment the snapshot was take this saves time . 
- After the new slave has caught up with the master is starts to accept reads .
- Failover is when the master node fails . When the master node fails what happens on a high levels on of the slaves temporarily becomes the master and accepts the writes . On a lower level this has problems as we need to decide which slave becomes the master . If we are using synchronous replication it is easy but in the case asynchronous different nodes have different sync states . 
- After the leader is back up we need to get ready to get back to writing changes but before that it has to catchup with all the changes that have happened after the failover .


### Replication Logs 

- Statement based replication is when we literally store the statements of the dml operations like update , insert and delete . While this looks fine , there is simple problem which makes this obsolete . Functions in the query such as now() , random execute differently due to small latency changes and probabilistic chance which can lead to data corruption . 
- 
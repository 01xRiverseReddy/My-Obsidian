

YouTube- Arpit Bhavani 


A database is just a process running on a server let’s say EC2 where other servers are accessing it through some port  , let’s say 3306 . 

You can choose to scale a db vertically or horizontally . Scaling vertically work as a temporary solution or works in aid to horizontally scaling but never as a stand alone solution . 

While scaling horizontally we create copies of databases known as shard and the process of creating this shards on different servers is called partitioning . 
Breaking data into separate chunks is called Sharding , the chunks are called shards . Whereas distributing these data into different servers is called partitioning . 

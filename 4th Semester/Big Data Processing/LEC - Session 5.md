Class: [[COMP6579001 - Big Data Processing]]
Session: 5
Topics: 
Date: 2023-03-25
Lecturer: [[D5544 - WAWAN CENGGORO, S.Kom., M.TI]]


### Outline

- HDFS (Hadoop Distributed File System)
- NoSQL
	- Key-Value DB (Redis, memcache)
	- Document-Oriented DB (MongoDB, ElasticSearch)
	- Wide Column DB (Cassandra, ScyllaDB, BigTable, HBase)
	- Graph DB (Neo4J)

# HDFS

HDFS has two types of nodes:
- Namenode (master): manages the filesystem namespace and stores the file metadata.
- Datanode (slave): stores data blocks and serve read & write requests.

![[Pasted image 20230325073408.png]]


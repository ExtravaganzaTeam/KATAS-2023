# Title

Database Availability

## Status

**accepted**

## Context

Databases are bottlenecks very often at higher scale. Especially relational databases usually not scale very well. Distributed databases like cassandra or elastic are scaling much better but are quite hard to manage at high scale. Data replication and eventual consistency are always problematic to implement in unstable networks.  

The nice part of scaling is automatic failover. It can take place if the primary server for the database fails. Failover is the term to describe the recovery process.  

High Availability refers to database systems that are set up so that standby servers can take over quickly when the master or primary server fails. To achieve high availability, a database system should meet some key requirements e.g.:  
* it should have redundancy to prevent single points of failure, 
* reliable switchover mechanisms, 
* active monitoring to detect any failures that may occur.

Setting up failover replication provides the needed redundancy to allow for high availability by ensuring that standbys are available if the master or primary server ever goes down.  

To not lost data when the database server crashes we should make regular data snapshots. The other method to protect data loss is data replication. It can have many uses:  
* OLTP Performance - removing reporting query load from the online transaction processing (OLTP) system improves both reporting query time and transaction processing performance,
* Fault Tolerance - in the event of master database server failure, the replica server can take over, since it already contains the master server’s data. In this configuration the replica server is also called the standby server. This configuration can also be used for regular maintenance of the primary server,
* Data Migration - to upgrade database server hardware, or to deploy the same system for another customer,
* Testing Systems in Parallel - when porting the application from one DBMS to another, the results on the same data from both the old and new systems must be compared to ensure that the new system works as expected.

Each database provider has its own mechanisms for data replication. The sample two mechanisms for Postgre database are described below:  

* In Single-Master Replication (SMR), changes to table rows in a designated master database server are replicated to one or more replica servers. The replicated tables in the replica database are not permitted to accept any changes (except from the master). But even if they do, changes are not replicated back to the master server.

* In Multi-Master Replication (MMR), changes to table rows in more than one designated master database are replicated to their counterpart tables in every other master database. In this model conflict resolution schemes are often employed to avoid problems like duplicate primary keys.

The data can be replicated in one direction only or in both directions. For Postgre database Single-Master Replication is also called unidirectional, since replication data flows in one direction only, from master to replica. Multi-Master Replication data, on the other hand, flows in both directions, and it is therefore called bidirectional replication.  

For distributed databases like Cassandra replication takes place in both directions. The replication factor says how many data replicas we want to store in a database cluster.  

## Decision

We have decided to scale operational database to more than one node in one datacenter to support higher load and availability.  
We have decided to scale analytical database to more than one node in one dataceter to support higher load and availability.  
We don't take under consideration whole operational databasese replication between datacenters located on different continents (only current trip data travels with traveler).  
Analytical data is not replicated between analytical databases in datacenters located on different continents.  

To guarantee an availability close to 100% it is necessary to implement a replica system that allows us to ensure that clients can work with another server when the main database server has to be disconnected to carry out maintenance tasks or expansion tasks. Anothre feature this replica system enables is that in the event of an uncontrolled drop in service, clients have another server to work with while the problem is resolved.  

## Consequences

Higher maintenance cost for databases management itself and for data replicas synchronisation after failures.  
Database failover takes some time and is not immediate.  
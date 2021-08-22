# Mongo and Mongoose

## SQL vs NoSQL: High-Level Differences

- SQL databases are primarily called as Relational Databases (RDBMS); whereas NoSQL database are primarily called as non-relational or distributed database.
- SQL databases are table based databases whereas NoSQL databases are document based, key-value pairs, graph databases or wide-column stores. 
- SQL databases have predefined schema whereas NoSQL databases have dynamic schema for unstructured data.
- SQL databases are vertically scalable whereas the NoSQL databases are horizontally scalable. - - SQL databases are scaled by increasing the horse-power of the hardware. NoSQL databases are scaled by increasing the databases servers in the pool of resources to reduce the load.
- SQL databases uses SQL ( structured query language ) for defining and manipulating the data, which is very powerful. In NoSQL database, queries are focused on collection of documents. 
- For complex queries: SQL databases are good fit for the complex query intensive environment whereas NoSQL databases are not good fit for complex queries. On a high-level, NoSQL don’t have standard interfaces to perform complex queries, and the queries themselves in NoSQL are not as powerful as SQL query language.

## SQL Database Examples

1. MySQL Community Edition

*The following are some of MySQL benefits and strengths:*

- Replication: By replicating MySQL database across multiple nodes the work load can be reduced heavily increasing the scalability and availability of business application
- Sharding: MySQL sharding os useful when there is large no of write operations in a high traffic website. 
- Memcached as a NoSQL API to MySQL: Memcached can be used to increase the performance of the data retrieval operations giving an advantage of NoSQL api to MySQL server.
- Maturity: This database has been around for a long time and tremendous community input and testing has gone into this database making it very stable.
- Wide range of Platforms and Languages: MySql is available for all major platforms like Linux, Windows, Mac, BSD and Solaris. It also has connectors to languages like Node.js, Ruby, C#, C++, C, Java, Perl, PHP and Python.
- Cost effectiveness: It is open source and free.

2. MS-SQL Server Express Edition

 *The following are some of MS-SQL benefits and strengths:*

- Integrated Development Environment: Microsoft visual studio, Sql Server Management Studio and Visual Developer tools provide a very helpful way for development and increase the developers productivity.
- Disaster Recovery: It has good disaster recovery mechanism including database mirroring, fail over clustering and RAID partitioning.
- Cloud back-up: Microsoft also provides cloud storage when you perform a cloud-backup of your database
3. Oracle Express Edition

*The following are some of Oracle benefits and strengths:*

- Easy to Upgrade: Can be easily upgraded to newer version, or to an enterprise edition.
- Wide platform support: It supports a wide range of platforms including Linux and Windows
- Scalability: Although the scalability of this database is not cost effective as MySQL server, but the solution is very reliable, secure, easily manageable and productive.

## NoSQL Database Examples

1. MongoDB

*The following are some of MongoDB benefits and strengths:*

- Speed: For simple queries, it gives good performance, as all the related data are in single document which eliminates the join operations.
- Scalability: It is horizontally scalable i.e. you can reduce the workload by increasing the number of servers in your resource pool instead of relying on a stand alone resource.
- Manageable: It is easy to use for both developers and administrators. This also gives the ability to shard database
- Dynamic Schema: Its gives you the flexibility to evolve your data schema without modifying the existing data

2. CouchDB

*The following are some of CouchDB benefits and strengths:*

- Schema-less: As a member of NoSQL family, it also have dynamic schema which makes it more flexible, having a form of JSON documents for storing data.
- HTTP query: You can access your database documents using your web browser.
- Conflict Resolution: It has automatic conflict detection which is useful while in a distributed database.
- Easy Replication: Implementing replication is fairly straight forward

3. Redis

*The following are some of Redis benefits and strengths:*

- Data structures: Redis provides efficient data structures to an extend that it is sometimes called as data structure server.
- Redis as Cache: You can use Redis as a cache by implementing keys with limited time to live to improve the performance.
- Very fast: It is consider as one of the fastest NoSQL server as it works with the in-memory dataset.
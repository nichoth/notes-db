# database notes

## consistency

### CAP theorem

[mongo blog on consistency](http://blog.mongodb.org/post/498145601/on-distributed-consistency-part-2-some)

**consistency** &ndash; all nodes see the same data at the same time  
**availability** &ndash; a guarantee that every request receives a response about whether it succeeded or failed  
**partition tolerance** &ndash; the system continues to operate despite arbitrary partitioning due to network failures  

* C class &ndash; strongly consistent (mongodb and relational)
* A class &ndash; high availability, eventual consistency (couchdb)

Availability in C class can be tuned via master-slave replication. Here there is a single node writing to the DB, many readers (slave nodes). The reads are eventually consistent.


## mongodb

key value store

Create an index on any field. Create an index on the `userid` field of the `records` collection:

    db.records.createIndex( { userid: 1 } )


### db per user

A collection is the equivalent of a relational DB table. Collections are containers for documents that share one or more indexes. Databases are groups of collections stored on disk using a single set of data files.



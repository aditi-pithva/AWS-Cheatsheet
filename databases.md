# AWS Database Services Cheat Sheet

## Amazon Database Services Overview
AWS offers a range of database services for different use cases, including relational, NoSQL, and in-memory databases, along with storage solutions.

---

## Amazon EBS (Elastic Block Store)
### What is EBS?
- Block storage service for use with Amazon EC2.
- Provides persistent, high-performance storage for single instances.

### Key Features:
1. **Volume Types**:
   - General Purpose SSD (gp3, gp2).
   - Provisioned IOPS SSD (io1, io2).
   - Throughput Optimized HDD (st1).
   - Cold HDD (sc1).
2. **Snapshots**:
   - Backup volumes to Amazon S3.
3. **Durability**:
   - Replicated within an Availability Zone.

### Use Cases:
- Boot volumes.
- High-performance workloads like databases.

---

## Amazon S3 (Simple Storage Service)
### What is S3?
- Object storage service designed for scalability, security, and durability.

### Key Features:
1. **Storage Classes**:
   - Standard, Intelligent-Tiering, Glacier, Deep Archive.
2. **Durability**: 99.999999999% (11 nines).
3. **Security**:
   - Encryption (SSE-S3, SSE-KMS, Client-side).
   - Bucket policies and access control.
4. **Scalability**: Virtually unlimited storage.

### Use Cases:
- Data backups, archival, and content delivery.
- Hosting static websites.

---

## Amazon RDS (Relational Database Service)
### What is RDS?
- Managed relational database service that supports multiple engines.

### Supported Engines:
- MySQL, PostgreSQL, MariaDB, Oracle, SQL Server, and Amazon Aurora.

### Key Features:
1. **Automatic Backups**.
2. **Multi-AZ Deployment** for high availability.
3. **Read Replicas** for scalability.
4. **Encryption** with KMS.

### Use Cases:
- Applications requiring relational databases.

---

## Amazon DynamoDB
### What is DynamoDB?
- A fully managed NoSQL database service designed for key-value and document-based applications.

### Key Features:
1. **Performance**: Single-digit millisecond response time.
2. **Scalability**: Automatic scaling based on workload.
3. **Backup & Restore**: Point-in-time recovery.
4. **Global Tables**: Multi-region replication.

### Use Cases:
- Real-time applications, IoT, mobile apps.

---

## Amazon Redshift
### What is Redshift?
- A fully managed data warehouse for big data analytics.

### Key Features:
1. **Massive Scalability**: Handle petabytes of data.
2. **Columnar Storage**: Optimized for analytics.
3. **Integration**: Connects with BI tools like Tableau, QuickSight.

### Use Cases:
- Business intelligence and analytics.
- Data lake integration.

---

## Amazon EFS (Elastic File System)
### What is EFS?
- Fully managed, elastic file storage for EC2 instances.

### Key Features:
1. **Scalability**: Automatically grows and shrinks.
2. **Shared Access**: Multiple EC2 instances can access the same file system.
3. **Storage Classes**:
   - Standard and Infrequent Access.

### Use Cases:
- Shared storage for applications and workloads.

---

## Amazon Neptune
### What is Neptune?
- Fully managed graph database service.

### Key Features:
1. **Supports Graph Models**: Property graph and RDF.
2. **Query Languages**:
   - Gremlin, SPARQL.
3. **Scalability**: Up to 15 read replicas.

### Use Cases:
- Social networks, fraud detection, recommendation engines.

---

## Amazon DocumentDB
### What is DocumentDB?
- Fully managed NoSQL document database service compatible with MongoDB.

### Key Features:
1. **Scalable**: Automatically scales compute and storage.
2. **Replication**: Six replicas across three AZs.
3. **Backup**: Continuous backups with point-in-time recovery.

### Use Cases:
- JSON-based applications.

---

## Amazon ElastiCache
### What is ElastiCache?
- Fully managed in-memory data store compatible with Redis and Memcached.

### Key Features:
1. **Low Latency**: Microsecond response times.
2. **Scalability**: Cluster mode for sharding.
3. **Replication**: Multi-AZ with failover.

### Use Cases:
- Caching, session management, gaming leaderboards.

---

## DynamoDB Accelerator (DAX)
### What is DAX?
- Fully managed caching service for DynamoDB that delivers up to a 10x performance improvement.

### Key Features:
1. **In-Memory Caching**: Reduces DynamoDB latency to microseconds.
2. **Compatibility**: No application code changes required.
3. **Multi-AZ Clusters** for high availability.

### Use Cases:
- High-performance applications using DynamoDB.

---

## Summary Table
| Service          | Type                     | Key Features                                | Use Cases                                   |
|------------------|--------------------------|---------------------------------------------|--------------------------------------------|
| **EBS**          | Block Storage            | Persistent, high-performance storage        | EC2 boot volumes, databases                |
| **S3**           | Object Storage           | Scalable, durable, and secure storage       | Data backups, static websites              |
| **RDS**          | Relational Database      | Multi-AZ, read replicas, managed backups    | Relational workloads, transactional data   |
| **DynamoDB**     | NoSQL Key-Value Store    | Millisecond latency, global tables          | Real-time apps, IoT                        |
| **Redshift**     | Data Warehouse           | Columnar storage, petabyte scale           | Analytics, BI                              |
| **EFS**          | Shared File Storage      | Elastic, shared file system                | Shared access for EC2 instances            |
| **Neptune**      | Graph Database           | Supports RDF, Gremlin                      | Social networks, recommendation engines    |
| **DocumentDB**   | NoSQL Document Store     | MongoDB-compatible, JSON support           | Content management, catalogs               |
| **ElastiCache**  | In-Memory Cache          | Microsecond latency, Redis/Memcached       | Caching, session management                |
| **DAX**          | DynamoDB Cache           | Microsecond latency for DynamoDB           | High-performance DynamoDB apps             |

---

## Best Practices
1. Use **EBS Snapshots** to back up your block storage.
2. Enable **S3 Lifecycle Policies** to optimize storage costs.
3. Use **RDS Multi-AZ** for high availability.
4. Leverage **DynamoDB Global Tables** for multi-region replication.
5. Utilize **ElastiCache** to reduce database query loads.
6. Implement **Neptune** for graph-based use cases like fraud detection.

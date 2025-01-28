# AWS Cloud Migration Cheat Sheet

## Migration Strategies (6 R's)
### 1. **Rehosting ("Lift and Shift")**
- Move applications to the cloud with minimal changes.
- Suitable for:
  - Legacy applications.
  - Quick migrations with tight timelines.
- Tools: AWS Application Migration Service (MGN).

### 2. **Replatforming ("Lift, Tinker, and Shift")**
- Make small optimizations to the application without significant architecture changes.
- Examples:
  - Migrating to managed services like RDS.
  - Updating an application to use Elastic Beanstalk.
- Benefits:
  - Improved scalability and performance with minimal effort.

### 3. **Refactoring/Re-architecting**
- Reimagine and re-architect the application for the cloud.
- Examples:
  - Breaking monolithic applications into microservices.
  - Leveraging serverless technologies like Lambda.
- Benefits:
  - Optimized for cost, scalability, and innovation.
- Challenges:
  - High upfront effort and cost.

### 4. **Repurchasing**
- Replace an existing application with a new solution.
- Examples:
  - Moving from an on-premises CRM to SaaS solutions like Salesforce.
  - Adopting AWS Marketplace software.
- Benefits:
  - Modern tools with no maintenance.

### 5. **Retaining**
- Keep some applications on-premises for specific reasons.
- Examples:
  - Regulatory compliance requirements.
  - Applications that need re-evaluation later.

### 6. **Retiring**
- Decommission outdated or unused applications.
- Benefits:
  - Reduces cost and complexity.

---

## AWS Cloud Adoption Framework (CAF)
### What is CAF?
- A framework to help organizations plan their cloud adoption journey.

### Perspectives:
1. **Business Perspectives**:
   - Align cloud strategies with business goals.
   - Focus on business value and ROI.
2. **People Perspectives**:
   - Upskill teams and align organizational structure.
3. **Governance Perspectives**:
   - Establish policies, compliance, and risk management.
4. **Platform Perspectives**:
   - Define the target architecture and foundational cloud infrastructure.
5. **Security Perspectives**:
   - Ensure secure cloud operations.
   - Align with regulatory requirements.
6. **Operations Perspectives**:
   - Enable efficient and resilient operations in the cloud.

---

## AWS Snow Family
### 1. **AWS Snowcone**
- Smallest device in the Snow Family.
- **Key Features**:
  - Edge computing, storage, and data transfer in rugged environments.
  - Lightweight, portable (weighs 4.5 lbs).
  - Capacity: 8TB usable storage.
  - Power via USB-C.
- Use Cases:
  - IoT data collection.
  - Offline data transfer to AWS.

### 2. **AWS Snowball**
- Larger, rugged device for edge computing and data transfer.
- **Key Features**:
  - Available in **Snowball Edge Storage Optimized** and **Snowball Edge Compute Optimized**.
  - Capacity: Up to 80TB usable storage.
  - Built-in compute with EC2 instances or Lambda.
- Use Cases:
  - Bulk data migration.
  - Edge analytics in remote locations.

### 3. **AWS Snowmobile**
- Exabyte-scale data transfer via a shipping container.
- **Key Features**:
  - Transfers up to 100PB per Snowmobile.
  - Secure transport with GPS tracking and encryption.
- Use Cases:
  - Large-scale migrations for enterprise data centers.
  - Data transfer for disaster recovery.

---

## Summary Table
| Migration Strategy         | Description                                                                 | Best Use Case                                               |
|----------------------------|-----------------------------------------------------------------------------|------------------------------------------------------------|
| **Rehosting**              | "Lift and shift" with minimal changes.                                     | Legacy applications, quick migrations.                     |
| **Replatforming**          | Minor optimizations during migration.                                       | Updating apps for managed services.                        |
| **Refactoring/Re-architecting** | Reimagine and optimize for the cloud.                                   | Building microservices, serverless architectures.          |
| **Repurchasing**           | Replace with SaaS or cloud-native solutions.                                | Moving to modern tools like Salesforce or AWS Marketplace. |
| **Retaining**              | Keep on-premises temporarily or permanently.                               | Apps with compliance or latency concerns.                  |
| **Retiring**               | Decommission outdated or unused applications.                              | Reduce cost and complexity.                                |

| Snow Family Service        | Description                        | Capacity/Features                                         | Best Use Case                             |
|----------------------------|------------------------------------|----------------------------------------------------------|------------------------------------------|
| **Snowcone**               | Small, portable edge device.       | 8TB storage, USB-C powered.                             | IoT, edge data collection.               |
| **Snowball**               | Rugged, medium-capacity device.    | Up to 80TB storage, built-in compute.                   | Bulk data migration, edge analytics.     |
| **Snowmobile**             | Massive data transfer container.   | Up to 100PB per Snowmobile.                             | Large-scale data center migration.       |

---

## Best Practices for Migration
1. Start with **discovery and assessment** of existing workloads.
2. Prioritize quick wins with **rehosting** or **replatforming**.
3. Use **Snow Family devices** for large-scale or offline data transfers.
4. Align migration with the **AWS Cloud Adoption Framework (CAF)**.
5. Leverage AWS migration tools such as **Application Migration Service** or **Database Migration Service** (DMS).
6. Plan for operational excellence by monitoring resources post-migration.

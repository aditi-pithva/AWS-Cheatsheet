# EC2 Cheat Sheet (AWS Cloud Practitioner Essentials)

## What is Amazon EC2?
Amazon Elastic Compute Cloud (EC2) is a web service that provides resizable compute capacity in the cloud. It allows you to launch virtual servers (instances) for your applications.

---

## Key Features of Amazon EC2
1. **Scalable Compute Capacity**:
   - Scale up or down based on demand.
2. **Elasticity**:
   - Quickly add or remove instances.
3. **Wide Selection of Instance Types**:
   - Optimized for various use cases (compute, memory, storage).
4. **Pay-as-You-Go Pricing**:
   - Pay only for the compute capacity you use.
5. **Secure Networking**:
   - Use VPCs to control inbound and outbound traffic.
6. **Flexible Storage Options**:
   - Attach EBS volumes, use instance store, or integrate with S3.

---

## EC2 Components
### 1. **Instances**
- Virtual servers that run applications.
- Types:
  - **General Purpose** (e.g., t2, t3, m5): Balanced compute, memory, and storage.
  - **Compute Optimized** (e.g., c5, c6g): High-performance compute.
  - **Memory Optimized** (e.g., r5, x2idn): Applications needing high memory.
  - **Storage Optimized** (e.g., i3, d2): High-performance storage needs.

### 2. **Amazon Machine Image (AMI)**
- Pre-configured templates for launching instances.
- Types:
  - AWS-provided AMIs.
  - Community AMIs.
  - Your own custom AMIs.

### 3. **Storage Options**
- **Elastic Block Store (EBS):** Persistent block storage.
- **Instance Store:** Temporary storage tied to the instance lifecycle.
- **Amazon S3:** Object storage for backups and archiving.

### 4. **Security Groups**
- Virtual firewalls controlling inbound and outbound traffic to your instance.
- Default behavior:
  - Allow all outbound traffic.
  - Deny all inbound traffic unless explicitly allowed.

### 5. **Elastic IP Addresses (EIPs)**
- Static public IP addresses for instances.
- Useful for services that require fixed IPs.

---

## Pricing Models
### 1. **On-Demand Instances**
- Pay for compute capacity by the hour or second.
- No upfront payment, suitable for short-term workloads.

### 2. **Reserved Instances**
- Commit to 1 or 3 years for significant cost savings.
- Types:
  - Standard: Up to 75% savings.
  - Convertible: Flexibility to change instance types.

### 3. **Spot Instances**
- Bid for unused EC2 capacity at reduced costs (up to 90% cheaper).
- Ideal for non-critical, interruptible workloads.

### 4. **Dedicated Hosts**
- Physical servers fully dedicated to your use.
- Useful for regulatory or licensing requirements.

---

## Key Concepts
### Elastic Load Balancing (ELB):
- Automatically distributes incoming application traffic across multiple instances.

### Auto Scaling:
- Automatically adjusts the number of EC2 instances to match demand.
- Types:
  - Dynamic Scaling: Responds to demand changes.
  - Predictive Scaling: Forecasts and scales in advance.

### Key Pairs:
- Used for secure SSH access to instances.
- Consists of a public key (stored on the instance) and a private key (stored locally).

### Placement Groups:
- Influence the placement of instances:
  - **Cluster**: Low-latency groups.
  - **Spread**: Instances spread across hardware for high availability.
  - **Partition**: Partitioned instances for large-scale workloads.

---

## Common EC2 Commands (CLI)
### Launch an Instance:
```bash
aws ec2 run-instances \
  --image-id <ami-id> \
  --count 1 \
  --instance-type <instance-type> \
  --key-name <key-pair-name> \
  --security-group-ids <security-group-id> \
  --subnet-id <subnet-id>
```

### List Running Instances:
```bash
aws ec2 describe-instances
```

### Stop an Instance:
```bash
aws ec2 stop-instances --instance-ids <instance-id>
```

### Terminate an Instance:
```bash
aws ec2 terminate-instances --instance-ids <instance-id>
```

### Allocate an Elastic IP:
```bash
aws ec2 allocate-address
```

### Attach an EBS Volume:
```bash
aws ec2 attach-volume \
  --volume-id <volume-id> \
  --instance-id <instance-id> \
  --device <device-name>
```

---

## Best Practices
1. Use **security groups** and **network ACLs** to control access.
2. Regularly update and patch instances.
3. Use **IAM roles** for granting permissions to instances.
4. Enable **CloudWatch monitoring** to track performance and costs.
5. Back up important data using **EBS snapshots** or **Amazon S3**.
6. Use **Elastic Load Balancer** and **Auto Scaling** for fault tolerance and high availability.

---

## Summary
Amazon EC2 is a core AWS service for scalable compute power. Understanding instance types, pricing models, and best practices is essential for optimizing costs and performance. Refer to the [AWS Documentation](https://docs.aws.amazon.com/ec2/index.html) for further details.


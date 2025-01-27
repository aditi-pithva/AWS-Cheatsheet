# AWS Networking Cheat Sheet

## Amazon VPC (Virtual Private Cloud)
### What is VPC?
- A **virtual network** dedicated to your AWS account.
- Allows you to launch AWS resources in a logically isolated network.
- Provides complete control over network configuration.

### Key Features:
1. **Subnetting**: Divide the VPC into private and public subnets.
2. **Route Tables**: Define traffic routing within the VPC.
3. **Internet Gateway (IGW)**: Allows public internet access for resources.
4. **NAT Gateway**: Enables outbound internet access for private subnets.
5. **Peering**: Connect two VPCs for communication.

---

## Security Group
### What is a Security Group?
- Acts as a **virtual firewall** for your instances.
- Controls **inbound** and **outbound** traffic.
- Operates at the **instance level**.

### Key Features:
1. **Stateful**:
   - Automatically allows responses to inbound traffic.
   - If inbound traffic is allowed, the outbound response is automatically allowed.
2. **Rules**:
   - Specify protocols, ports, and IP ranges.

### Example:
```bash
Inbound Rule:
  - Allow HTTP traffic: Port 80, Source: 0.0.0.0/0
Outbound Rule:
  - Allow all traffic.
```

---

## Stateless vs. Stateful
### Stateful:
- Automatically tracks the state of connections.
- Example: Security Groups.

### Stateless:
- Does not track the state of connections.
- Explicit rules are required for both inbound and outbound traffic.
- Example: Network ACLs.

---

## Route 53
### What is Route 53?
- A **scalable Domain Name System (DNS)** web service.
- Translates domain names (e.g., `example.com`) into IP addresses.

### Key Features:
1. **Domain Registration**: Register domain names.
2. **DNS Routing Policies**:
   - Simple, Weighted, Latency-based, Geolocation, Failover, Multi-Value Answer.
3. **Health Checks**: Monitor endpoints and route traffic based on their status.
4. **Traffic Flow**: Advanced routing control across multiple regions.

---

## Subnets
### What is a Subnet?
- A subdivision of a VPC.
- Resources in subnets can be public or private.

### Types:
1. **Public Subnet**:
   - Connected to the Internet Gateway.
   - Hosts resources like web servers.
2. **Private Subnet**:
   - No direct internet access.
   - Hosts sensitive resources like databases.

### Key Points:
- Subnet **CIDR blocks** must be within the VPC CIDR block.
- Subnets are **associated with a single Availability Zone (AZ)**.

---

## Network ACL (Access Control List)
### What is a Network ACL?
- Acts as a **firewall** for controlling traffic at the **subnet level**.

### Key Features:
1. **Stateless**:
   - Rules must be explicitly defined for both inbound and outbound traffic.
2. **Rules**:
   - Evaluated in order by **rule number** (lowest to highest).
   - Example:
     - Allow: Port 80, Source: 0.0.0.0/0, Rule #: 100
     - Deny: All, Rule #: 200
3. **Default Behavior**:
   - Default ACL allows all traffic.
   - Custom ACL denies all traffic unless explicitly allowed.

---

## Key Networking Services and Components
### Internet Gateway (IGW):
- Allows resources in a public subnet to access the internet.
- Scalable, redundant, and highly available.

### NAT Gateway:
- Allows outbound internet access for instances in private subnets.
- Does not allow inbound connections.

### Elastic IP (EIP):
- A static, public IP address that can be associated with an instance.
- Useful for hosting applications requiring a fixed IP.

### VPC Peering:
- Establishes a connection between two VPCs to enable communication.
- Peered VPCs can be in the same or different AWS accounts.

---

## Summary Table
| Component         | Description                                   | Key Features                                      |
|-------------------|-----------------------------------------------|--------------------------------------------------|
| **VPC**           | Virtual network for AWS resources.            | Subnets, Route Tables, IGW, NAT Gateway.         |
| **Security Group**| Virtual firewall for instances.               | Stateful, allows inbound and outbound rules.     |
| **Network ACL**   | Firewall at subnet level.                     | Stateless, ordered rules, applies to all traffic.|
| **Subnets**       | Subdivide VPC into public/private sections.   | Tied to one AZ, has its own CIDR block.          |
| **Route 53**      | DNS web service.                              | Domain registration, routing policies, health checks.|
| **Internet Gateway**| Provides public internet access.            | Used for public subnets.                         |
| **NAT Gateway**   | Outbound internet access for private subnets. | Scalable, no inbound access.                     |

---

## Best Practices
1. Use **Security Groups** for fine-grained instance-level control.
2. Implement **Network ACLs** for subnet-level security.
3. Design **subnets** for proper segmentation of public and private resources.
4. Leverage **Route 53 health checks** for failover and routing.
5. Enable **flow logs** on VPC for network monitoring and troubleshooting.
6. Use **VPC Peering** or **Transit Gateway** for secure inter-VPC communication.

---

## Common CLI Commands
### Create a VPC:
```bash
aws ec2 create-vpc --cidr-block 10.0.0.0/16
```

### Create a Subnet:
```bash
aws ec2 create-subnet --vpc-id <vpc-id> --cidr-block 10.0.1.0/24 --availability-zone <az>
```

### Create a Security Group:
```bash
aws ec2 create-security-group --group-name <name> --description <desc> --vpc-id <vpc-id>
```

### Add Inbound Rule to Security Group:
```bash
aws ec2 authorize-security-group-ingress \
  --group-id <sg-id> \
  --protocol tcp \
  --port 22 \
  --cidr 0.0.0.0/0
```

### Create a Route Table:
```bash
aws ec2 create-route-table --vpc-id <vpc-id>
```


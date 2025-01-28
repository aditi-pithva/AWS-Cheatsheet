# AWS Security Services Cheat Sheet

## AWS Shared Responsibility Model
### What is the Shared Responsibility Model?
AWS divides security responsibilities between AWS and the customer:

1. **AWS Responsibilities** (Security *of* the Cloud):
   - Physical security of data centers.
   - Networking, hardware, and software that run AWS services.

2. **Customer Responsibilities** (Security *in* the Cloud):
   - Data protection.
   - Identity and access management.
   - Configuring network and application-level security.

### Key Takeaway:
- AWS manages infrastructure security.
- Customers manage application and data security.

---

## AWS Identity and Access Management (IAM)
### What is IAM?
- A service to control access to AWS resources securely.

### Key Features:
1. **Users, Groups, Roles**:
   - Users: Individual accounts.
   - Groups: Collections of users with shared permissions.
   - Roles: Grant temporary permissions to entities.
2. **Policies**:
   - JSON documents to define permissions.
3. **MFA (Multi-Factor Authentication)**:
   - Adds an extra layer of security.

### Best Practices:
- Grant least privilege.
- Use roles instead of hardcoding credentials.
- Enable MFA for all users.

---

## AWS Organizations
### What is AWS Organizations?
- A service to centrally manage multiple AWS accounts.

### Key Features:
1. **Consolidated Billing**: Single bill for all accounts.
2. **Service Control Policies (SCPs)**: Define permissions across accounts.
3. **Account Management**: Create and manage accounts programmatically.

### Use Cases:
- Centralized account management.
- Enforcing compliance policies.

---

## AWS Shield
### What is AWS Shield?
- A managed DDoS protection service.

### Key Features:
1. **Shield Standard**:
   - Automatic protection against common DDoS attacks.
   - Included for free.
2. **Shield Advanced**:
   - Additional protection for large-scale attacks.
   - 24/7 support and cost protection for scaling.

### Use Cases:
- Protecting web applications from DDoS attacks.

---

## AWS Compliance Services
### What are AWS Compliance Services?
- AWS offers tools and certifications to help meet compliance requirements.

### Key Tools:
1. **AWS Artifact**:
   - Access AWS compliance reports.
2. **AWS Config**:
   - Track resource configurations for compliance.
3. **Audit Manager**:
   - Automate evidence collection for audits.

### Certifications:
- SOC, PCI DSS, ISO 27001, HIPAA.

---

## AWS Key Management Service (KMS)
### What is KMS?
- A managed service to create and control cryptographic keys.

### Key Features:
1. **Encryption**:
   - Encrypt data at rest and in transit.
2. **Key Management**:
   - Manage symmetric and asymmetric keys.
3. **Integration**:
   - Works with S3, EBS, RDS, Lambda, and more.

### Best Practices:
- Rotate keys regularly.
- Use customer-managed keys for additional control.

---

## AWS WAF (Web Application Firewall)
### What is WAF?
- Protects web applications from common exploits like SQL injection and cross-site scripting (XSS).

### Key Features:
1. **Rules**:
   - Predefined or custom rules to filter traffic.
2. **Integration**:
   - Works with CloudFront, ALB, and API Gateway.
3. **Real-time Monitoring**:
   - View blocked requests and traffic insights.

### Use Cases:
- Securing web applications.
- Blocking malicious IPs and bots.

---

## AWS Inspector
### What is AWS Inspector?
- A vulnerability management service.

### Key Features:
1. **Automated Assessments**:
   - Identify vulnerabilities in EC2 instances and container images.
2. **CIS Benchmarks**:
   - Checks against best practices.
3. **Reports**:
   - Prioritize vulnerabilities based on severity.

### Use Cases:
- Vulnerability scanning for compliance.
- Securing EC2 and container environments.

---

## AWS GuardDuty
### What is GuardDuty?
- A threat detection service to monitor malicious activities and unauthorized behavior.

### Key Features:
1. **Machine Learning**:
   - Detect anomalies in AWS account activity.
2. **Integration**:
   - Monitors CloudTrail, VPC Flow Logs, and DNS logs.
3. **Threat Intelligence**:
   - Uses AWS-managed threat databases.

### Use Cases:
- Detecting compromised accounts.
- Identifying unusual API calls or network behavior.

---

## Summary Table
| Service           | Purpose                                         | Key Features                                  |
|-------------------|-------------------------------------------------|----------------------------------------------|
| **IAM**           | Manage access to AWS resources.                | Users, roles, policies, MFA.                 |
| **Organizations** | Centrally manage multiple AWS accounts.        | SCPs, consolidated billing.                  |
| **Shield**        | DDoS protection.                               | Standard (free), Advanced (premium).         |
| **Compliance**    | Tools for meeting regulatory requirements.     | AWS Artifact, Config, Audit Manager.         |
| **KMS**           | Key management and encryption.                 | Key rotation, integration with AWS services. |
| **WAF**           | Web application firewall.                      | SQL injection protection, real-time insights.|
| **Inspector**     | Vulnerability scanning.                        | CIS benchmarks, automated assessments.       |
| **GuardDuty**     | Threat detection.                              | ML-based anomaly detection, threat intel.    |

---

## Best Practices
1. Use **IAM policies** to enforce the principle of least privilege.
2. Enable **AWS Shield Advanced** for critical applications.
3. Regularly scan your environment with **Inspector**.
4. Use **GuardDuty** to detect and respond to anomalies.
5. Implement **MFA** for all user accounts.
6. Encrypt sensitive data with **KMS**.
7. Use **AWS Config** to track compliance.
8. Protect web applications with **WAF** rules.


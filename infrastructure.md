# AWS Infrastructure Cheat Sheet

## AWS Regions
### What are AWS Regions?
- **Regions** are physical locations around the world where AWS operates.
- Each region consists of multiple **Availability Zones** (AZs).
- Regions are isolated to provide fault tolerance and minimize latency.

### Key Features:
1. **Data Residency**: Data stays in the region unless explicitly moved.
2. **Global Reach**: 30+ regions worldwide (e.g., `us-east-1`, `eu-west-1`).
3. **Pricing**: Costs vary by region.
4. **Service Availability**: Not all services are available in every region.

### When to Choose a Region:
- **Latency**: Choose the closest region to your users.
- **Compliance**: Ensure data meets residency requirements.
- **Cost**: Select regions with lower costs if latency and compliance allow.

---

## Availability Zones (AZs)
### What are Availability Zones?
- **AZs** are isolated data centers within a region.
- Connected by low-latency, high-bandwidth networks.

### Benefits:
1. **High Availability**: Deploy across multiple AZs for fault tolerance.
2. **Isolation**: Faults in one AZ do not affect others.
3. **Scalability**: Add resources in other AZs seamlessly.

---

## Edge Locations
### What are Edge Locations?
- **Edge Locations** are data centers used by AWS services like Amazon CloudFront to cache content closer to users.
- Part of the AWS **Content Delivery Network (CDN)**.

### Key Features:
1. **Low Latency**: Serve cached content closer to end-users.
2. **Global Reach**: 400+ edge locations worldwide.
3. **Services**:
   - CloudFront (content delivery).
   - Route 53 (DNS).
   - Lambda@Edge (serverless execution at edge).

---

## AWS Outposts
### What is AWS Outposts?
- AWS-managed infrastructure that brings AWS services to your **on-premises data center**.

### Key Features:
1. **Hybrid Cloud**: Run AWS services on-premises.
2. **Consistent Experience**: Use the same AWS APIs, tools, and services.
3. **Use Cases**:
   - Low-latency applications.
   - Data residency requirements.

---

## Amazon CloudFront
### What is CloudFront?
- A **Content Delivery Network (CDN)** service that delivers content globally with low latency and high transfer speeds.

### Key Features:
1. **Caching**: Stores content at edge locations.
2. **Security**: Integrated with AWS Shield and WAF.
3. **Dynamic & Static Content**: Serves websites, APIs, and media.

### Common Use Cases:
- Accelerating website performance.
- Streaming video and audio.
- Securing and distributing APIs.

---

## AWS Elastic Beanstalk
### What is Elastic Beanstalk?
- A **Platform as a Service (PaaS)** for deploying and managing applications.

### Key Features:
1. **Simplified Deployment**: Just upload your code, and Elastic Beanstalk handles deployment, scaling, and monitoring.
2. **Supports Multiple Languages**: Java, Python, Node.js, .NET, PHP, Ruby, etc.
3. **Customizability**: You retain full control over AWS resources.

### Common Use Cases:
- Web applications.
- APIs.
- Backend services.

---

## AWS CloudFormation
### What is CloudFormation?
- An **Infrastructure as Code (IaC)** service that allows you to define and provision AWS resources using templates.

### Key Features:
1. **Templates**:
   - Written in YAML or JSON.
   - Define the resources and configurations.
2. **Automation**: Automates resource creation and updates.
3. **Drift Detection**: Identifies resources that have been changed manually.

### Example Use Case:
```yaml
Resources:
  MyS3Bucket:
    Type: "AWS::S3::Bucket"
    Properties:
      BucketName: "example-bucket"
```

### Benefits:
- **Repeatability**: Consistent resource creation across environments.
- **Version Control**: Track changes to infrastructure.
- **Dependency Management**: Automatically handles dependencies between resources.

---

## Summary Table
| Feature                | Description                                         |
|------------------------|-----------------------------------------------------|
| **Regions**            | Geographical locations with multiple AZs.          |
| **Availability Zones** | Isolated data centers within a region.             |
| **Edge Locations**     | Global caching locations for low latency.          |
| **Outposts**           | AWS services on-premises for hybrid cloud setups.  |
| **CloudFront**         | Content delivery network for fast global delivery. |
| **Elastic Beanstalk**  | PaaS for deploying and managing applications.      |
| **CloudFormation**     | IaC for managing AWS infrastructure.               |

---

## Best Practices
1. Use **multiple AZs** for high availability.
2. Deploy **CloudFront** to improve global performance.
3. Utilize **CloudFormation templates** for repeatable infrastructure.
4. For hybrid cloud needs, consider **AWS Outposts**.
5. Leverage **Edge Locations** for low-latency content delivery.



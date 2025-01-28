# AWS Monitoring and Management Cheat Sheet

## Amazon CloudWatch
### What is CloudWatch?
- A monitoring and observability service for AWS resources and applications.

### Key Features:
1. **Metrics**:
   - Collect and track metrics from AWS services and custom applications.
2. **Logs**:
   - Collect, monitor, and analyze log data from EC2, Lambda, and other services.
3. **Alarms**:
   - Set alarms based on metrics to trigger actions (e.g., scaling or notifications).
4. **Dashboards**:
   - Create custom dashboards to visualize metrics and logs.
5. **Events**:
   - Respond to changes in your environment using CloudWatch Events.

### Use Cases:
- Monitor application performance.
- Troubleshoot issues using logs and metrics.
- Automate responses to system changes.

### Common Commands:
```bash
# List metrics for a service
aws cloudwatch list-metrics --namespace AWS/EC2

# Put a custom metric
aws cloudwatch put-metric-data --namespace MyApp --metric-name PageViews --value 100

# Create an alarm
aws cloudwatch put-metric-alarm \
  --alarm-name HighCPUUsage \
  --metric-name CPUUtilization \
  --namespace AWS/EC2 \
  --statistic Average \
  --period 300 \
  --threshold 80 \
  --comparison-operator GreaterThanThreshold \
  --evaluation-periods 2 \
  --alarm-actions <SNS_topic_ARN>
```

---

## AWS CloudTrail
### What is CloudTrail?
- A service that enables governance, compliance, and operational auditing by recording AWS account activity.

### Key Features:
1. **Event History**:
   - Provides a history of AWS API calls and console actions.
2. **Trails**:
   - Create trails to deliver logs to an S3 bucket for long-term storage.
3. **Multi-Region Tracking**:
   - Monitor API activity across all regions.
4. **Insights**:
   - Detect unusual activity patterns automatically.

### Use Cases:
- Audit changes to AWS resources.
- Track API call history for security and compliance.
- Detect unusual activities in your account.

### Common Commands:
```bash
# List trails
aws cloudtrail describe-trails

# Create a new trail
aws cloudtrail create-trail \
  --name MyTrail \
  --s3-bucket-name my-trail-logs-bucket

# Lookup events (e.g., API calls)
aws cloudtrail lookup-events --lookup-attributes AttributeKey=EventName,AttributeValue=StartInstances
```

---

## AWS Trusted Advisor
### What is Trusted Advisor?
- A tool that provides insights and recommendations to optimize your AWS environment.

### Key Categories:
1. **Cost Optimization**:
   - Identify unused or underutilized resources.
2. **Performance**:
   - Improve service performance.
3. **Security**:
   - Check for security gaps (e.g., exposed access keys).
4. **Fault Tolerance**:
   - Enhance the resilience of your applications.
5. **Service Limits**:
   - Monitor usage against service limits.

### Use Cases:
- Reduce costs by identifying idle resources.
- Enhance security by following best practices.
- Optimize performance and ensure fault tolerance.

### Key Features:
- **Basic Checks**: Included with all AWS accounts.
- **Full Checks**: Available with Business or Enterprise Support plans.

### Common Trusted Advisor Checks:
- Security groups with open ports.
- MFA-enabled on root accounts.
- Unassociated Elastic IP addresses.
- Underutilized EC2 instances.

---

## Summary Table
| Service         | Purpose                                      | Key Features                                  | Use Cases                                   |
|-----------------|----------------------------------------------|----------------------------------------------|--------------------------------------------|
| **CloudWatch**  | Monitor AWS resources and applications.      | Metrics, logs, alarms, dashboards, events.   | Performance monitoring, automated responses.|
| **CloudTrail**  | Record AWS account activity for auditing.    | Event history, trails, insights.             | Security auditing, API tracking.           |
| **Trusted Advisor** | Optimize AWS environment.                | Cost optimization, security, performance.    | Reduce costs, enhance security, fault tolerance.|

---

## Best Practices
1. Use **CloudWatch Dashboards** to monitor key metrics in real-time.
2. Enable **CloudTrail** in all regions to track account activity globally.
3. Regularly review **Trusted Advisor** recommendations to optimize costs and security.
4. Set up **CloudWatch Alarms** for critical resources to respond to threshold breaches.
5. Use **CloudTrail Insights** to detect anomalies and unusual API activity.

# IAM, IAM Users, and IAM Roles Cheat Sheet

## Identity and Access Management (IAM)
### What is IAM?
- A service provided by AWS to manage access to AWS resources securely.
- Ensures that only authenticated and authorized entities can access AWS services and resources.

### Key Features:
1. **Centralized control**: Manage permissions across AWS resources.
2. **Granular Permissions**: Allow fine-tuned access control.
3. **Shared Access**: Enable multiple users or services to access AWS.
4. **Temporary Access**: Provide short-term access through roles.
5. **Identity Federation**: Support for SAML, OpenID Connect, and other identity providers.
6. **Audit & Compliance**: Track changes and access through AWS CloudTrail.

### IAM Entities:
- **IAM Users**: Represents individual people or systems requiring long-term credentials.
- **IAM Groups**: Collections of users that share permissions.
- **IAM Roles**: Used to grant temporary access to AWS resources for users or services.
- **IAM Policies**: JSON documents that define permissions.

---

## IAM User
### What is an IAM User?
- Represents a single user or system.
- Comes with long-term credentials like an Access Key ID and Secret Access Key.

### Key Points:
1. **Permissions**: Assigned via policies.
2. **Credentials**:
   - **Console Access**: Username and password.
   - **Programmatic Access**: Access Key ID and Secret Access Key.
3. **Best Practices**:
   - Grant the least privilege necessary.
   - Avoid sharing credentials.
   - Enable MFA (Multi-Factor Authentication).

### When to Use IAM Users?
- For employees needing long-term access to AWS.
- For applications requiring specific, non-temporary permissions.

---

## IAM Role
### What is an IAM Role?
- Similar to a user but does not have permanent credentials.
- Can be assumed by entities like:
  - IAM users.
  - AWS services (e.g., EC2, Lambda).
  - External accounts (via identity federation).

### Key Points:
1. **Assume Role**:
   - Roles are assumed using the `sts:AssumeRole` API call.
   - Provides temporary credentials.
2. **Use Cases**:
   - Applications running on EC2 needing S3 access.
   - Cross-account access.
   - Temporary access for federated users.
3. **Best Practices**:
   - Limit role assumption to specific entities.
   - Grant least privilege.
   - Rotate access by using temporary credentials.

### When to Use IAM Roles?
- For temporary access requirements.
- To avoid managing long-term credentials.
- To allow AWS services to interact securely with one another.

---

## IAM Policies
### What are IAM Policies?
- JSON documents defining permissions.

### Types:
1. **Managed Policies**:
   - AWS Managed: Predefined by AWS.
   - Customer Managed: Created by users.
2. **Inline Policies**:
   - Embedded directly in a user, group, or role.

### Structure:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:ListBucket",
      "Resource": "arn:aws:s3:::example-bucket"
    }
  ]
}
```

### Best Practices:
- Follow the principle of least privilege.
- Use AWS managed policies for common use cases.
- Test policies with the IAM Policy Simulator.

---

## Summary
| Feature        | IAM User              | IAM Role                      |
|----------------|-----------------------|-------------------------------|
| **Credentials**| Long-term             | Temporary                     |
| **Use Cases**  | Employees, applications | Cross-account, AWS services  |
| **MFA**        | Yes                   | Not applicable (assume role credentials) |
| **Permissions**| Via policies          | Via policies                  |

---

## Commands to Know
- **Create IAM User**:
  ```bash
  aws iam create-user --user-name <username>
  ```
- **Attach Policy to User**:
  ```bash
  aws iam attach-user-policy --user-name <username> --policy-arn <policy_arn>
  ```
- **Create Role**:
  ```bash
  aws iam create-role --role-name <role_name> --assume-role-policy-document file://<policy_file>.json
  ```
- **Assume Role**:
  ```bash
  aws sts assume-role --role-arn <role_arn> --role-session-name <session_name>
  ```

---

## Next Steps
- Commit this cheat sheet to your GitHub repository:
  ```bash
  git add IAM_Cheat_Sheet.md
  git commit -m "Add IAM cheat sheet"
  git push origin main
  ```
- Review AWS IAM documentation for deeper understanding: [AWS IAM Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/)


Storage

| Features                       | My Recommendation                                            | AWS S3                                                      | GCP Cloud Storage                                            | Azure Blob Storage                                            |
|-------------------------------|-------------------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------------|--------------------------------------------------------------|
| Object Storage                 | Use for unstructured data, versioning, scalability          | Objects in buckets, 5 TB limit per object, versioning, tags  | Buckets for objects, unified object/file/archive storage      | Blobs in containers, block/page/append blobs, versioning      |
| Storage Classes                | Analyze data access and use lifecycle policies              | Standard, Intelligent-Tiering, IA, Glacier, Deep Archive     | Standard, Nearline, Coldline, Archive, Autoclass              | Hot, Cool, Archive, Premium, automatic tiering                |
| Encryption                     | Always enable encryption at rest and in transit             | SSE-S3 (default), SSE-KMS, SSE-C, TLS 1.2/1.3                | Default, CMEK, CSEK, TLS/SSL                                  | AES 256-bit, Key Vault, encryption in transit                 |
| Access Control (IAM)           | Apply least privilege, audit policies regularly             | IAM roles, bucket policies, MFA Delete, OIDC/SAML, Access Points | IAM policies, service accounts, group roles, policy analyzer  | RBAC via Azure AD, SAS tokens, policy assignment              |
| Data Protection/Resiliency     | Enable replication/versioning/backup for critical data      | Cross/replication, object lock, 99.999999999% durability     | Multi-region replication, object/bucket lock, strong consistency| Geo-redundancy, point-in-time restore, immutability, soft delete|
| Lifecycle Management           | Automate transitions for cost savings, timely purging       | Lifecycle rules, Intelligent Tiering, object expiration      | Automated policies for transitions, duration/size-based rules  | Rules for auto-tiering, purging, archiving                    |
| Network Security               | Isolate data, restrict to VPC/private endpoints, enforce TLS| VPC endpoints, source IP restrictions, HTTPS/TLS, Block Public Access | VPC Service Controls, private endpoints, TLS, firewall rules | Private endpoints, virtual network, firewall/IP restriction    |
| API Security                   | Use signed URLs/tokens, enforce access, monitor activity    | Pre-signed URLs, request signing, HTTPS-only, CloudTrail     | Signed URLs, API-level keys, CMEK/CSEK, audit logging         | SAS tokens, network rules, monitoring with Security Center     |
| Monitoring & Compliance        | Log all access, set alerts for suspicious activity          | Storage Lens, CloudTrail, Macie for sensitive data, logging  | Audit logs, monitoring, bucket access reports, alerts          | Azure Monitor, audit logging, compliance policies              |

This format aligns features, actionable recommendations, and vendor-specific capabilities side-by-side for quick practical reference.

Citations:
[1] Amazon S3 Features - Cloud Object Storage - AWS https://aws.amazon.com/s3/features/
[2] Amazon S3 - Cloud Object Storage - AWS https://aws.amazon.com/s3/
[3] What is Amazon S3? - Amazon Simple Storage Service https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html
[4] Object Storage Classes – Amazon S3 - AWS https://aws.amazon.com/s3/storage-classes/
[5] Introduction to AWS Simple Storage Service (AWS S3) https://www.geeksforgeeks.org/introduction-to-aws-simple-storage-service-aws-s3/
[6] GCP Cloud Storage 2025 - The Complete Guide Step By Step https://gcpmasters.in/gcp-cloud-storage/
[7] Azure Blob Storage: Features, Usage, And Steps to Create https://k21academy.com/microsoft-azure/admin/azure-blob-storage/
[8] AWS Features and Pricing in 2025: A Detailed Guide for Businesses https://bminfotrade.com/blog/cloud-computing/aws-features-and-pricing-in-2025
[9] Product overview of Cloud Storage | Google Cloud https://cloud.google.com/storage/docs/introduction
[10] Azure Blob Storage https://azure.microsoft.com/en-in/products/storage/blobs
[11] Amazon S3 - Wikipedia https://en.wikipedia.org/wiki/Amazon_S3

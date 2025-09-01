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


--------------------------------------------------------------------------------------------------------------------------

Provide me the full table.

Here is the full detailed table incorporating all key storage service features, with "My Recommendation" segmented into Must Have, Good to Have, and Optional categories for AWS S3, GCP Cloud Storage, and Azure Blob Storage:

| Features               | My Recommendation                           | AWS S3                             | GCP Cloud Storage                  | Azure Blob Storage                  |
|------------------------|---------------------------------------------|----------------------------------|----------------------------------|----------------------------------|
| Object Storage         | Must Have: Use versioning for critical data | Objects organized in buckets; versioning, tagging | Buckets for objects; unified storage, versioning | Blobs in containers; versioning, multiple blob types |
| Storage Classes        | Must Have: Match data access frequency to storage class; automate transitions | Standard, Intelligent-Tiering, IA, Glacier, Deep Archive | Standard, Nearline, Coldline, Archive, Autoclass | Hot, Cool, Cold, Archive, Premium, auto-tiering |
| Encryption             | Must Have: Encrypt at rest and in-transit;<br>Good to Have: Customer-managed keys | Server-side encryption (SSE-S3, SSE-KMS); TLS | CMEK/CSEK, TLS/SSL | AES-256, Azure Key Vault integration, TLS |
| IAM & Access Control   | Must Have: Least privilege policies;<br>Good to Have: Regular audits | IAM roles, bucket policies, MFA delete | IAM policies, service accounts, fine-grained roles | RBAC via Azure AD, SAS tokens |
| Data Protection/Resiliency | Must Have: Enable replication/versioning;<br>Good to Have: Automated backup | Cross-region replication, object lock, 11 nines durability | Multi-region replication, strong consistency | Geo-redundancy, versioning, soft delete, immutability |
| Lifecycle Management   | Must Have: Automate lifecycle rules;<br>Good to Have: Purge obsolete data | Lifecycle policies, Intelligent Tiering | Automated transitions, duration/size-based rules | Tiering policies, auto-purge rules |
| Network Security       | Must Have: Private endpoints, restrict public access;<br>Good to Have: Enforce TLS | VPC endpoints, Block Public Access, IP restrictions | VPC Service Controls, enforced TLS | Private endpoints, firewall/IP rules, VNet integration |
| API Security           | Must Have: Signed URLs/tokens;<br>Good to Have: Monitor API calls | Pre-signed URLs, CloudTrail monitoring | Signed URLs, audit logging | SAS tokens, Security Center monitoring |
| Monitoring & Compliance| Must Have: Enable logging and alerts;<br>Good to Have: Audit access regularly | Storage Lens, CloudTrail, Macie | Audit logs, access reports | Azure Monitor, audit logs, compliance policies |

This table provides a comprehensive overview aligned with your preferred format for actionable best practices and key cloud object storage features for AWS, GCP, and Azure.

Citations:
[1] S3 Vs. GCS Vs. Azure Blob Storage https://airbyte.com/data-engineering-resources/s3-gcs-and-azure-blob-storage-compared
[2] Compare AWS and Azure services to Google Cloud https://cloud.google.com/docs/get-started/aws-azure-gcp-service-comparison
[3] Cloud Storage Pricing Comparison: AWS S3, GCP, Azure ... https://www.backblaze.com/cloud-storage/pricing
[4] Compare Storage Services on Azure and AWS https://learn.microsoft.com/en-us/azure/architecture/aws-professional/storage
[5] Storage services compared: AWS vs Azure vs GCP https://www.pluralsight.com/resources/blog/cloud/storage-showdown-aws-vs-azure-vs-gcp-cloud-comparison
[6] Amazon S3 vs Google Cloud Storage vs Azure Pricing ... https://www.msp360.com/resources/blog/amazon-s3-azure-and-google-cloud-prices-compare/
[7] Amazon S3 vs Google Cloud Storage vs Azure Storage Cost https://www.economize.cloud/blog/amazon-s3-vs-google-storage-vs-azure-storage/
[8] Comprehensive Comparison of Cloud Storage: GCP, AWS, ... https://www.ijera.com/papers/vol15no3/15032735.pdf
[9] Cloud Pricing Comparison: AWS vs. Azure vs. Google in ... https://cast.ai/blog/cloud-pricing-comparison/

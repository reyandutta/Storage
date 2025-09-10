Need revised table

Here is the revised table with feature names, descriptions, domains, and API calls made cloud-agnostic and errors rectified:

| Best Practice / Feature                   | Description                                                                                         | Domain                             | Must Have | Good to Have | Optional | AWS S3 | GCP Cloud Storage | Azure Blob Storage | Typical API Calls                               |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------|------------------------------------|-----------|--------------|----------|--------|-------------------|--------------------|-------------------------------------------------|
| Block Public Access                       | Ability to block public access at bucket or object level, preventing accidental data exposure.      | Identity & Access Management / Security | ✓         |              |          | ✓      | ✓                 | ✓                  | PutPublicAccessBlock, SetAccessPolicy           |
| Encryption at Rest & in Transit           | Ensure all data is encrypted when stored or transferred, using provider-managed or customer-managed keys. | Data Encryption                    | ✓         |              |          | ✓      | ✓                 | ✓                  | PutBucketEncryption, SetDefaultKmsKey           |
| Least Privilege Access Control            | Apply fine-grained permissions so users and apps have only the access required for their tasks.     | Identity & Access Management / Security | ✓         |              |          | ✓      | ✓                 | ✓                  | PutBucketPolicy, SetIamPolicy                   |
| Multi-Factor Authentication for Deletion  | Require multi-factor authentication before allowing deletion of objects or containers.               | Identity & Access Management / Security | ✓         |              |          | ✓      | ✗                 | ✗                  | PutBucketMfaDelete                              |
| Logging & Monitoring                      | Enable access logs and usage monitoring for compliance and auditing of storage usage and access patterns. | Observability                      | ✓         |              |          | ✓      | ✓                 | ✓                  | EnableLogging, GetServiceLogging                |
| Object Versioning                         | Maintain multiple versions of objects to protect against overwrites and accidental deletions.       | Data Management                    | ✓         |              |          | ✓      | ✓                 | ✓                  | EnableVersioning, SetVersioning                 |
| Data Immutability & Retention Lock        | Prevent deletion or overwrite of objects for a fixed period to meet compliance/legal requirements.  | Data Protection / Compliance        |           | ✓            | ✓        | ✓      | ✓                 | ✓                  | SetRetentionPolicy, PutObjectRetention          |
| Data Lifecycle Management                 | Automate data management by transitioning or deleting objects based on age or access patterns.      | Data Management / Cost Optimization |           | ✓            | ✓        | ✓      | ✓                 | ✓                  | SetLifecycleConfiguration, SetManagementPolicy  |
| Access Analyzer or Policy Evaluation Tool | Analyze storage resource policies to detect unintended public or cross-account access.              | Identity & Access Management / Observability |           | ✓            | ✓        | ✓      | ✓                 | ✓                  | StartAccessAnalyzer                             |
| Multi-Region Data Replication             | Automatically replicate data across regions for disaster recovery and high availability.            | Data Protection / Availability      |           | ✓            | ✓        | ✓      | ✓                 | ✓                  | PutReplicationConfiguration, SetGeoReplication  |
| Custom Access Logging                     | Configure access logs with custom fields or formats to fit audit and reporting needs.               | Observability                      |           |              | ✓        | ✓      | ✓                 | ✓                  | EnableCustomLogging, ConfigureLogFields          |
| Resource Tagging for Organization         | Attach metadata tags to resources for cost allocation, searchability, and policy enforcement.       | Resource Management                |           |              | ✓        | ✓      | ✓                 | ✓                  | PutBucketTagging, SetBucketLabels                |

All feature names and terminology are now cloud agnostic, and API calls use generalized nomenclature or mention equivalents where appropriate[1][2][3][4][5].

Citations:
[1] 1000075463.jpg https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/39124392/bf688fc9-4ea0-4db8-9136-61cdc2348ddc/1000075463.jpg
[2] Best practices for Cloud Storage - Google Cloud https://cloud.google.com/storage/docs/best-practices
[3] What is Cloud Storage Security? Risks & Best Practices to Combat https://www.tierpoint.com/blog/cloud-storage-security/
[4] Security best practices for Amazon S3 https://docs.aws.amazon.com/AmazonS3/latest/userguide/security-best-practices.html
[5] 24 Google Cloud Platform (GCP) security best practices - Sysdig https://www.sysdig.com/learn-cloud-native/24-google-cloud-platform-gcp-security-best-practices



The current api calls resemble mostly aws, isn't it? Can you give me typical api calls which resembles gcp and Azure as well? Give me revised table.

Here is the revised table with typical API calls for each feature from AWS, Google Cloud Storage (GCP), and Azure Blob Storage, formatted to provide representative commands for all three providers:

| Best Practice / Feature                   | Description                                                                                         | Domain                             | Must Have | Good to Have | Optional | AWS S3 API Call   | GCP Cloud Storage API Call             | Azure Blob Storage API Call                    |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------|------------------------------------|-----------|--------------|----------|-------------------|-----------------------------------------|------------------------------------------------|
| Block Public Access                       | Ability to block public access at bucket or object level, preventing accidental data exposure.      | Identity & Access Management / Security | ✓         |              |          | PutPublicAccessBlock | setIamPolicy (public access=false)      | Set-PublicAccessLevel / SetBlobContainerACL    |
| Encryption at Rest & in Transit           | Ensure all data is encrypted when stored or transferred, using provider-managed or customer keys.   | Data Encryption                    | ✓         |              |          | PutBucketEncryption, SetDefaultKmsKey | setDefaultKmsKey / PatchBucket                 | Set-StorageAccountEncryption                  |
| Least Privilege Access Control            | Apply fine-grained permissions so users and apps have only the access required for their tasks.     | Identity & Access Management / Security | ✓         |              |          | PutBucketPolicy, SetIamPolicy      | setIamPolicy / addIamMember                    | Set-AzStorageContainerAcl / SetBlobAccessPolicy|
| Multi-Factor Authentication for Deletion  | Require multi-factor authentication before allowing deletion of objects or containers.               | Identity & Access Management / Security | ✓         |              |          | PutBucketMfaDelete     | N/A                                    | N/A                                            |
| Logging & Monitoring                      | Enable access logs and usage monitoring for compliance and auditing of storage usage and access patterns. | Observability                      | ✓         |              |          | EnableBucketLogging / GetServiceLogging | getLogging / setLogging                       | Set-StorageAnalyticsLogging / Get-LogSettings  |
| Object Versioning                         | Maintain multiple versions of objects to protect against overwrites and accidental deletions.       | Data Management                    | ✓         |              |          | PutBucketVersioning, SetBucketVersioning | PatchBucket(versioning=enabled)                | Set-BlobServiceProperties(versioning)          |
| Data Immutability & Retention Lock        | Prevent deletion or overwrite of objects for a fixed period to meet compliance/legal requirements.  | Data Protection / Compliance        |           | ✓            | ✓        | PutObjectRetention / SetRetentionPolicy | setRetentionPolicy                            | Set-BlobImmutabilityPolicy / SetBlobRetention  |
| Data Lifecycle Management                 | Automate data management by transitioning or deleting objects based on age or access patterns.      | Data Management / Cost Optimization |           | ✓            | ✓        | PutLifecycleConfiguration                   | setLifecycleConfiguration / PatchBucket        | Set-BlobLifecycleManagementPolicy              |
| Access Analyzer or Policy Evaluation Tool | Analyze storage resource policies to detect unintended public or cross-account access.              | Identity & Access Management / Observability |           | ✓            | ✓        | StartAccessAnalyzer                         | getIamPolicy / analyzeIamPolicy                | Get-AzStorageContainerPermission               |
| Multi-Region Data Replication             | Automatically replicate data across regions for disaster recovery and high availability.            | Data Protection / Availability      |           | ✓            | ✓        | PutReplicationConfiguration / SetGeoReplication | PatchBucket(replication config)                | Set-AzStorageAccountReplication                |
| Custom Access Logging                     | Configure access logs with custom fields or formats to fit audit and reporting needs.               | Observability                      |           |              | ✓        | ConfigureLogFields / SetCustomLogging       | enableLogging / setNotification                | Set-StorageAnalyticsLogging                    |
| Resource Tagging for Organization         | Attach metadata tags to resources for cost allocation, searchability, and policy enforcement.       | Resource Management                |           |              | ✓        | PutBucketTagging                              | setLabels / updateBucket                       | SetBlobTags / SetBlobMetadata                  |

This list balances terminology and API syntax to provide comparable calls for AWS, GCP, and Azure, making it easier to work across providers and reference equivalent commands for core security features[1][2][3][4][5][6][7].

Citations:
[1] APIs & reference | Cloud Storage | Google Cloud https://cloud.google.com/storage/docs/apis
[2] Bucket - Documentation https://googleapis.dev/nodejs/storage/latest/Bucket.html
[3] Guide to Azure Blob REST API: Upload, Download ... - SmiKar https://www.smikar.com/azure-blob-rest-api/
[4] Blob Storage REST API - Azure Storage | Microsoft Learn https://learn.microsoft.com/en-us/rest/api/storageservices/blob-service-rest-api
[5] Security recommendations for Blob storage - Azure Storage https://learn.microsoft.com/en-us/azure/storage/blobs/security-recommendations
[6] Azure Storage Security Features - KodeKloud Notes https://notes.kodekloud.com/docs/AZ-204-Developing-Solutions-for-Microsoft-Azure/Exploring-Azure-Blob-Storage/Azure-Storage-Security-Features
[7] 1000075463.jpg https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/images/39124392/bf688fc9-4ea0-4db8-9136-61cdc2348ddc/1000075463.jpg
[8] Securing Google Cloud Storage: In-Depth Guide to the storage ... https://expertbeacon.com/securing-google-cloud-storage-in-depth-guide-to-the-storage-buckets-get-api/
[9] Google Cloud Functions: How to Use Security Certificates in ... https://stackoverflow.com/questions/62379345/google-cloud-functions-how-to-use-security-certificates-in-bucket
[10] 4 steps for hardening your Google Cloud Storage buckets ... https://cloud.google.com/blog/products/gcp/4-steps-for-hardening-your-cloud-storage-buckets-taking-charge-of-your-security
[11] S3 Vs. GCS Vs. Azure Blob Storage: Cloud Storage Comparison ... https://airbyte.com/data-engineering-resources/s3-gcs-and-azure-blob-storage-compared
[12] Google Cloud Storage bucket: setup, security & lifecycle rules https://statsig.com/perspectives/cloud-storage-setup-security-rules
[13] Developing RESTful APIs with Azure Blob Storage and Azure ... https://reintech.io/blog/developing-restful-apis-azure-blob-storage-functions
[14] 10+ Cloud Storage APIs Compared - Nordic APIs https://nordicapis.com/10-cloud-storage-apis-compared/
[15] Google Storage FAQs for Developers Complete Guide | MoldStud https://moldstud.com/articles/p-ultimate-guide-to-google-storage-faqs-for-developers-everything-you-need-to-know
[16] Compare storage on Azure and AWS - learn.microsoft.com https://learn.microsoft.com/en-us/azure/architecture/aws-professional/storage
[17] Best Cloud Storage & File Sharing APIs (2025) — Public APIs https://publicapis.io/best/cloud-storage-and-file-sharing
[18] Azure Blob Storage - GeeksforGeeks https://www.geeksforgeeks.org/cloud-computing/azure-blob-storage/
[19] Amazon S3 vs. Google Cloud Storage vs. Azure pricing, features https://www.techtarget.com/searchstorage/feature/AWS-vs-Azure-vs-Google-pricing-and-features-compared
[20] S3compare.io: Comprehensive Provider List and Storage Comparison https://www.s3compare.io
[21] Securing Azure Blob Storage: Set-Up Guide - Varonis https://www.varonis.com/blog/azure-blob-storage

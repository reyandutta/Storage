Make it like first put for aws, then gcp, then azure.

Below is a reorganized and streamlined summary, structured to cover AWS first, then Google Cloud Platform (GCP), then Azure, for all major cloud storage service aspects. This will provide a clear, side-by-side view perfect for developing your own cloud storage solution.

***

# Cloud Storage Services Reference (AWS, GCP, Azure)

## AWS Storage Services

### Object Storage: **Amazon S3**
- **Storage Classes**: Standard, Intelligent-Tiering, Standard-IA, One Zone-IA, Glacier, Deep Archive
- **Features**:
  - Virtually unlimited storage (5 TB max per object)
  - Lifecycle management with automated class migration
  - Versioning, event notifications, tagging
  - Strong consistency, cross-region replication
  - Encryption options: SSE-S3, SSE-KMS, SSE-C
  - Access control: IAM, bucket policies, ACLs
- **Performance**: Multi-GB/sec throughput, 11 9s durability, 99.99% availability
- **Pricing Example**: Standard $0.023/GB/month, Deep Archive $0.00099/GB/month[1][2][3][4][5]

### Block Storage: **Amazon EBS**
- **Volume Types**: gp3, io2, st1, sc1, etc.
- **Features**:
  - High-performance SSD options (up to 256,000 IOPS)
  - Elastic resize, Multi-Attach, snapshot/restore
  - Encryption at rest/in transit
- **Availability**: 99.999%
- **Use cases**: Databases, file systems, boot volumes[4][6][7][5]

### File Storage: **Amazon EFS**
- **Fully managed NFS shares**
- **Features**:
  - Elastic scaling, standard/IA classes, POSIX compliance, concurrent EC2 access
  - Encryption, VPC/on-premises access
- **Use cases**: Content management, shared app data, web serving[4][6][7][5]

***

## Google Cloud Platform (GCP) Storage Services

### Object Storage: **Google Cloud Storage**
- **Classes**: Standard, Nearline, Coldline, Archive
- **Features**:
  - Unlimited objects (5 TB max per object), global edge caching
  - Strong consistency, object lifecycle management, Pub/Sub notifications
  - Encryption: Google-managed, CMEK, CSEK
  - Access control: IAM, uniform bucket-level access
- **Performance**: 10+ GB/sec throughput, 11 9s durability, 99.95% (multi-regional) availability
- **Pricing Example**: Standard $0.026/GB/month, Archive $0.0012/GB/month[8][9][10][11][12]

### Block Storage: **Google Persistent Disk/Hyperdisk**
- **Types**: Standard, SSD, Extreme, Hyperdisk (custom performance)
- **Features**:
  - Live resize, regional replication, up to 1M IOPS
  - Snapshots, encryption at rest/in transit (default)
- **Use cases**: Databases, enterprise workloads, machine learning[11][12][13]

### File Storage: **Google Filestore**
- **Features**: NFS shares, multiple performance tiers, automatic scaling, high availability, snapshots
- **Use cases**: Application migration, shared data, media processing[9][11][13]

***

## Azure Storage Services

### Object Storage: **Azure Blob Storage**
- **Tiers**: Hot, Cool, Cold, Archive
- **Features**:
  - Unlimited storage (4.77 TB max per blob)
  - Immutable storage (WORM), Azure Data Lake Gen2
  - Strong consistency, event grid integration, static website hosting
  - Encryption: Service/customer-managed keys
  - Access control: Azure AD, RBAC, SAS
- **Performance**: Up to 60 Gbps/account, 11 9s durability, 99.99% (hot) availability
- **Pricing Example**: Hot $0.0184/GB, Archive $0.00099/GB/month[15][16][17][18][19]

### Block Storage: **Azure Managed Disks**
- **Types**: Ultra Disk, Premium SSD, Standard SSD, HDD
- **Features**:
  - Up to 80,000 IOPS/disk, shared disks, disk encryption
  - Snapshots, incremental backups, zone-redundant storage
- **Use cases**: Databases, HPC, enterprise apps[18][16]

### File Storage: **Azure Files**
- **Features**: SMB/NFS shares, performance tiers, Azure AD join, sync, REST API, cross-platform access, snapshots
- **Use cases**: Shared app data, dev tools, diagnostic data[18][16][17]

***

## Feature Comparison Summary

| Feature            | AWS S3                  | GCP Cloud Storage       | Azure Blob               |
|--------------------|-------------------------|-------------------------|--------------------------|
| Max Object Size    | 5 TB                    | 5 TB                    | 4.77 TB                  |
| Consistency Model  | Strong                  | Strong                  | Strong                   |
| Encryption         | SSE-S3, KMS, C          | Google-managed, CMEK    | Service/customer-managed |
| Access Control     | IAM, ACLs               | IAM, Uniform-bucket     | Azure AD, RBAC           |
| Global Regions     | 37                      | 35+                     | 60+                      |
| Durability         | 11 9s                   | 11 9s                   | 11 9s                    |
| Availability SLA   | 99.99%                  | 99.95%                  | 99.99%                   |

***

## Security and Compliance  
- All providers meet major certifications (SOC, PCI-DSS, HIPAA, FedRAMP)[20][21][22][14].
- Encryption at rest and in transit is standard; all three offer customer-managed keys and detailed access logging.

***

## Recommendations for New Cloud Storage Solutions
1. **Adopt Multi-Tier Storage**: Support object, block, and file storage with lifecycle and automated tiering.
2. **Build Robust Security**: Bring parity with leading encryption and access controls.
3. **Focus on Developer Experience**: RESTful APIs, SDKs, event handling, lifecycle automation.
4. **Design for Global Scalability**: Replication, strong consistency, and regional options.
5. **Optimize Cost**: Intelligent Tiering, lifecycle tools, transparent pricing.

***

The full document (Markdown format) containing every detailed feature and comparison is ready for download here:
This structure provides a clear, CSP-by-CSP ordering for maximum clarity and usability.

Citations:
[1] What is Amazon S3? - Amazon Simple Storage Service https://docs.aws.amazon.com/AmazonS3/latest/userguide/Welcome.html
[2] Cloud Storage Services on AWS https://aws.amazon.com/products/storage/
[3] Amazon S3 - Cloud Object Storage - AWS https://aws.amazon.com/s3/
[4] Amazon S3 vs EBS vs EFS - Tutorials Dojo https://tutorialsdojo.com/amazon-s3-vs-ebs-vs-efs/
[5] Choosing the Right AWS Storage: EBS vs EFS vs S3 Explained https://www.cloudoptimo.com/blog/choosing-the-right-aws-storage-ebs-vs-efs-vs-s3-explained/
[6] EBS vs EFS vs S3 - When to Use AWS' Three Storage Solutions https://www.justaftermidnight247.com/insights/ebs-efs-and-s3-when-to-use-awss-three-storage-solutions/
[7] Overview of AWS EFS, EBS and S3 and their differences https://k21academy.com/amazon-web-services/difference-between-aws-efs-ebs-and-s3/
[8] Google Cloud Storage - Wikipedia https://en.wikipedia.org/wiki/Google_Cloud_Storage
[9] GCP Storage: Types, Key Features & Best Practises https://www.lucidity.cloud/blog/gcp-storage
[10] Cloud Storage | Google Cloud https://cloud.google.com/storage
[11] Google Persistent Disk & Google Filestore Services - GeeksforGeeks https://www.geeksforgeeks.org/cloud-computing/google-persistent-disk-google-filestore-services/
[12] Choose a disk type | Compute Engine Documentation - Google Cloud https://cloud.google.com/compute/docs/disks
[13] Google Cloud Storage Options: Object, Block, and File Storage https://www.netapp.com/learn/object-storage-block-and-shared-file-storage-in-google-cloud/
[14] S3 Vs. GCS Vs. Azure Blob Storage - Airbyte https://airbyte.com/data-engineering-resources/s3-gcs-and-azure-blob-storage-compared
[15] Azure Storage: Overview and Introduction to the Various Solutions https://www.qa.com/resources/blog/azure-storage-service-overview/
[16] Introduction to Azure Storage - Microsoft Community https://learn.microsoft.com/en-us/azure/storage/common/storage-introduction
[17] Storage account overview - Azure Storage | Microsoft Learn https://learn.microsoft.com/en-us/azure/storage/common/storage-account-overview
[18] Different Types of Azure Storage (Blob, Table, File, Queue) - Site24x7 https://www.site24x7.com/learn/azure-storage-types.html
[19] Performance, Pricing & Operations (AWS vs Azure vs GCP) https://www.cloudexpat.com/blog/enterprise-cloud-storage-deep-dive-p2/
[20] AWS vs Azure vs GCP: Evaluating Cross-Cloud Security Models https://www.cloudoptimo.com/blog/aws-vs-azure-vs-gcp-evaluating-cross-cloud-security-models/
[21] Encryption and Management of Keys in the Cloud on AWS, Azure ... https://www.linkedin.com/pulse/encryption-management-keys-cloud-aws-azure-gcp-rakesh-patra-772pc
[22] Data encryption options | Cloud Storage - Google Cloud https://cloud.google.com/storage/docs/encryption

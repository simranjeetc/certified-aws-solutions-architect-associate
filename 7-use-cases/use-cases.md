#### How to prevent deletion of important documents indefinitely using Amazon S3 Glacier Vault

1. Set a legal hold on the formulation document archive in the vault
2. Use vault lock policy to match the LegalHold tag and deny deletion of the formulation document archive

Vault Lock Policy: Provides a way to lock the vault's policy for a specified period or indefinitely, preventing changes to the policy after it is locked.

Legal Hold: Typically used in litigation or investigation scenarios where data needs to be preserved until the hold is removed. This would prevent deletion while the hold is in place.


#### How to deny all accounts in AWS org from creating an S3 bucket with public access

Enable Amazon S3 block public access on AWS org's service control policies(SCPs) to deny users making change to these settings

- SCPs (Service control policies) assist in centrally controlling permissions for all accounts in AWS Organizations. This helps to ensure that all the accounts in AWS Organizations are following the same access guidelines.
- Amazon S3 Block Public Access settings can be used to manage public access to Amazon S3 buckets. By default, all the new buckets created in Amazon S3 do not support public access. But users can change these settings to allow public access to the bucket.
- Block Public Access settings can be used to deny permission to users from making changes to public access to the bucket.
- SCP can be applied at the Organization Root-level to deny all accounts permission to make S3 buckets public.

#### What is used for accessing VPCs across different regions
VPC Peering - efficient for inter-region traffic and avoids public internet routing

#### How to provide connectivity between AWS VPCs and on-premises networks over the public internet?
VPN Connections

#### How to connect services across different accounts and VPCs without exposing traffic to the public internet?
AWS PrivateLink

#### What is the best AWS service for simple, direct VPC-to-VPC connections across different regions?
Inter-Region VPC Peering is the most suitable service for straightforward VPC-to-VPC connections across regions. It facilitates private IP communication between resources in different regions without requiring complex network setups, ensuring that traffic does not traverse the public internet.

#### Which AWS service should be used for managing complex multi-region network architectures that involve multiple VPCs and hybrid networks?
AWS Transit Gateway is ideal for large-scale or complex network environments involving multiple VPCs across regions. It acts as a central hub, simplifying the management of network connections and scaling dynamically with organizational needs, thus providing centralized management and monitoring.

#### What AWS solution is recommended for organizations requiring consistent, high-throughput, low-latency connections from on-premises data centers to AWS?
AWS Direct Connect is recommended for dedicated connectivity needs. It provides a direct connection from on-premises networks to AWS, bypassing the public internet. This service is crucial for applications that require consistent network performance, offering both reliability and enhanced security.

#### When should a VPN be used for connecting on-premises networks to AWS VPCs, especially across regions?
A VPN Connection is suitable when dedicated connectivity is impractical or too expensive. It securely extends an on-premises network to AWS VPCs over the internet and is particularly useful for organizations that need encrypted, flexible, and cost-effective connections without significant initial investments.

#### How can AWS services be utilized to securely connect services across different accounts and regions without exposing data to the public internet?
AWS PrivateLink is the best option for securely connecting services across VPCs and accounts without public internet exposure. It's especially useful for internal service sharing or connecting with external partners while minimizing the attack surface by avoiding public IP addresses and simplifying security management.

Certainly! Here's how the options from the text can be formatted into a question-and-answer format, focusing on the use cases each AWS service is best suited for:

#### Which AWS service should I use to identify objects, people, text, scenes, and activities in images and videos, and to analyze facial details?
Amazon Rekognition is the ideal service for these tasks. It provides capabilities to identify various elements within images and videos, offers facial analysis, and has advanced search capabilities for detecting, analyzing, and comparing faces. 

#### I need a service for extracting text, handwriting, and other data from scanned documents, including forms and tables. Which AWS service should I use?
Amazon Textract is a fully managed machine learning service that automatically extracts printed text, handwriting, and other data from scanned documents. It goes beyond simple optical character recognition (OCR) to identify, understand, and extract data from forms and tables effectively.

#### Which AWS service is best for natural language processing to analyze text and uncover insights such as sentiment and relationships?
Amazon Comprehend is the best choice for natural language processing tasks. It utilizes machine learning to analyze text for sentiment, key phrases, entities, and language. It's primarily used for uncovering valuable insights and connections in text but is not suitable for text-to-speech conversions.

#### If I need to convert text into lifelike speech for creating applications that talk, which AWS service should I use?
Amazon Polly is the service designed for converting text into lifelike speech, enabling the development of applications that can speak and respond to users. It supports multiple languages and voices, making it ideal for building speech-enabled products and services.

#### How can I efficiently manage intermittent "too many connections" errors and performance slowdowns in an Amazon RDS MySQL database, especially when facing high demand and bursty traffic in an e-commerce environment?
 Use Amazon RDS Proxy. 
 - RDS Proxy acts as an intermediary service that pools and shares database connections, improving database efficiency and application scalability. This service helps manage the database connections by allowing them to be reused, which significantly reduces the connection overhead for applications that open and close connections frequently. 
 - Additionally, RDS Proxy enhances the ability to handle bursty workloads, which are common in e-commerce platforms, without needing to provision excess database connections, thus streamlining operations and reducing the chance of database performance bottlenecks.

#### How can I effectively track and record API calls between a web server and an application server to diagnose communication issues?
Use AWS CloudTrail for tracking and recording API calls. 

#### What AWS service should I use to perform automated security assessments to identify vulnerabilities or unintended network exposures in my applications?
Amazon Inspector

#### If I need to collect logs for troubleshooting and want a visual representation of service integrations and communications, which AWS service should I use?
AWS X-Ray 

#### For analyzing and debugging distributed microservices architecture, especially to understand communication between web and application servers, which AWS service offers the best integration and visualization tools?
Amazon X-Ray 

#### How can I perform real-time analytics(heavy queries) on transactional data without impacting the performance of my operational database?
Amazon Aurora Parallel Query is the optimal solution for this scenario. 
- It enables you to perform analytical queries directly on the data stored in your transactional Aurora MySQL database without the need to transfer data to a separate analytics system i.e. without slowing down your live database operations.

#### I need to analyze log data and monitor real-time applications without a dedicated analytics database. Which AWS service should I use?
Amazon OpenSearch (formerly known as Amazon Elasticsearch) is suitable for log analytics, real-time application monitoring, and clickstream analysis. 

#### For processing vast amounts of data for big data applications, which AWS service is recommended?
Amazon EMR (Elastic MapReduce) is recommended for big data processing use cases. It supports various big data frameworks, including Apache Hadoop and Apache Spark, and is ideal for tasks that require processing large datasets, complex analytics, and data transformations. EMR is particularly effective in environments where data is batch-processed from various sources.

#### Which AWS service should I use to create interactive dashboards and visualizations from my data sources for business intelligence?
Amazon QuickSight is the best choice for building interactive dashboards and visualizations. 

### An organization is planning to move its employee self-service applications from on-premises data centers to AWS Cloud. The organization has millions of users in its Corporate Directory on-premises. They need a way to provide access to all applications that would be migrated to the cloud after users log in to their on-premises employee portal. Additionally, they aim to extend access to other cloud-based applications like Salesforce in the future. What is the best solution to have users on-premises access the applications in AWS?

The best solution in this scenario is to use AWS IAM Identity Center to sign-on users defined in the Corporate Directory on-premises with SAML 2.0 based identity federation for accessing the AWS applications. AWS IAM Identity Center is a cloud-based single sign-on service that allows for central management of single sign-on across different AWS accounts and cloud applications. It provides flexibility by integrating with AWS-managed Microsoft AD, on-premises AD services, and any identity provider that is SAML 2.0 compliant.

This approach allows the organization to leverage its existing on-premises identity provider and avoid duplicating users in IAM, ensuring a seamless integration and access management to cloud applications like Salesforce, Jenkins, and others directly through AWS IAM Identity Center, thereby aligning with the organization's requirements for a hybrid cloud model.

#### A company wants to monitor the performance of their EC2 instances, such as CPU utilization, and receive alerts when usage goes beyond 80%, potentially indicating performance issues or the need for scaling.
CloudWatch

#### A company needs to ensure that all administrative actions, such as launching or terminating EC2 instances, modifying security groups, or configuring other AWS services, are recorded for compliance with IT security standards and auditing.
CloudTrail

Based on the provided content, here are the Q&A formatted notes focusing on use-case scenarios related to AWS services for security management:

#### A company wants to aggregate, organize, and prioritize security alerts or findings across multiple AWS services using automated security checks based on AWS security best practices. Which AWS service should they use to manage this in a centralized manner?
AWS Security Hub

#### In a scenario where both security and operational issues need to be managed and remediated, which AWS service can provide detailed insights and data that can be used to understand and mitigate these concerns independently or in a combined manner?
AWS Systems Manager Ops Center

#### If a business needs to manage and remediate operational issues within their AWS environment, which service allows for the automation of these tasks and helps in ensuring operational health?
AWS Systems Manager

#### Which AWS service is used to protect applications from Distributed Denial of Service (DDoS) attacks, ensuring that applications remain available and performant?
AWS Shield

#### When a company needs to manage and remediate security issues within their AWS environment, which service offers capabilities to handle these security challenges effectively?
AWS Security Hub

#### An organization requires detailed assessments and remediation related to **network** accessibility of EC2 instances. Which AWS service can provide this type of security assessment information?
AWS Inspector

#### The Utopia Municipality Corporation runs its applications locally but has its database on an on-premise data center while keeping the application server in EC2. They need a solution that allows all AWS services to communicate seamlessly with their on-premises database without migrating or hosting it in the cloud, ensuring compliance and a consistent hybrid experience. What AWS service should they use?
- AWS Outposts delivers AWS infrastructure and services to virtually any on-premises or edge location, providing a truly consistent hybrid experience. It is fully managed and supports local processing and data residency, which aligns with the organization's requirement for low-latency access to on-premises systems without migrating the database to AWS.
- AWS DataSync is an online data transfer service that simplifies, automates, and accelerates moving data into AWS. Like Snowball Edge, it conflicts with the organization's policy against migrating their database to the cloud.
- While AWS Storage Gateway facilitates the integration of on-premises environments with cloud storage, it is primarily used for backup solutions and would not support the real-time, low-latency interaction required between AWS services and the on-premises database without hosting data in the cloud.

AWS PrivateLink vs VPC Peering
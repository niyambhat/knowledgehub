---
sidebar_position: 4
---

# AWS

# AWS S3 bucket
Amazon S3 is an object storage service that offers industry-leading scalability, data availability, security, and performance. AWS S3 (Amazon Simple Storage Service) is a highly scalable cloud storage service provided by Amazon Web Services (AWS). It allows you to store and retrieve large amounts of data from anywhere on the web. Here's a brief overview of AWS S3:

* Object Storage: S3 provides object storage, which means you can store and retrieve any type of data, such as images, videos, documents, and backups, as objects. Each object consists of the data itself, a unique key (identifier), and metadata.
* Durability and Availability: S3 is designed for durability and high availability. It automatically stores multiple copies of your data across multiple servers and facilities within an AWS region. This redundancy ensures that your data is highly durable and available.
* Scalability: S3 scales seamlessly to support virtually unlimited storage and request volume. You can start with a small amount of data and scale up as your storage needs grow.
* Security: S3 provides multiple security features to help protect your data. These include access control mechanisms like bucket policies and access control lists (ACLs), server-side encryption, and integration with AWS Identity and Access Management (IAM).
* Data Management: S3 offers various features for managing your data. You can organize your objects into buckets, which act as logical containers. S3 also supports versioning, allowing you to preserve, retrieve, and restore previous versions of objects.
* Access Control: With S3, you can control access to your data at both the bucket and object levels. You can define access policies, grant permissions to specific users or groups, and use AWS IAM to manage authentication and authorization.
* Data Transfer: S3 provides multiple methods for transferring data in and out of the service. This includes direct uploads and downloads using the AWS Management Console or SDKs, as well as integration with other AWS services like AWS Transfer Family, AWS DataSync, and AWS Snowball for large-scale data transfer.
* Cost-Effective: S3 offers a cost-effective storage solution with flexible pricing options. You only pay for the storage you use, and there are no upfront costs or long-term commitments. S3 also provides features like lifecycle policies and storage classes (such as Standard, Intelligent-Tiering, Glacier, and others) to optimize storage costs based on your data access patterns.
* Integration and Ecosystem: S3 integrates with a wide range of AWS services and tools, making it a central storage solution for many cloud-based applications and architectures. It also has a large ecosystem of third-party applications and services that support S3 integration.

AWS S3 is widely used for various purposes, including data backup and archiving, website hosting, content distribution, big data analytics, and serving static assets for web applications. It provides a reliable, scalable, and secure storage solution in the AWS cloud environment.

Photography Image Storage App for photographer

https://medium.com/the-freelancer/store-your-images-with-aws-s3-60b7ac167f8b

# List of Amazon Services

* Amazon EC2:
Example: You can use Amazon EC2 to run a website or web application. To do this, you would launch an EC2 instance, install the necessary software and configure the instance to run your application, and then host your website or web application on that instance. You can also use EC2 to run other types of applications, such as machine learning models or batch processing jobs.

* Amazon S3:
Example: You can use Amazon S3 to store and retrieve files or objects, such as images or videos. For example, you can upload your files to an S3 bucket, which is a container for storing objects, and then retrieve those files from anywhere with an internet connection. You can also use S3 to host a static website, by enabling the static website hosting feature and configuring your website's content.

* Amazon RDS:
Example: You can use Amazon RDS to create a managed relational database in the cloud. For example, if you have an application that requires a MySQL database, you can launch an RDS instance running MySQL, and then connect your application to that instance. RDS takes care of managing the database, including backups, software patching, and scaling.

* Amazon DynamoDB:
Example: You can use Amazon DynamoDB to create a highly-scalable NoSQL database in the cloud. For example, if you have an application that requires a flexible, low-latency database, you can create a DynamoDB table and store your data in that table. DynamoDB can automatically scale to handle high volumes of read and write traffic, and can be used for a wide range of applications, such as mobile and web applications, gaming, and IoT.
# Overview of Project
In this project, you will design and implement a multi-tier web application architecture on AWS. The primary goal is to create a robust, scalable, and secure environment that meets the best practices for modern cloud architecture. By leveraging AWS services, you will build an application infrastructure that maximizes availability, enhances security, and supports the seamless scaling of resources.

# Project Goals
* Scalability: Implement an architecture that can automatically scale up or down based on demand.
* Availability: Ensure that the application remains highly available, even in the event of failures in certain components.
* Security: Secure the application by isolating different layers of the architecture and applying strict security controls.

# Architectural Diagram
This it the architectural diagram for the project:

![architecture](https://github.com/user-attachments/assets/74340842-c8ad-4c7e-b7fb-be47140166b5)

# Architecture Overview
The architecture of the multi-tier web application will consist of three main tiers, each serving distinct functions within the application. This approach ensures a separation of concerns, improves scalability, enhances security, and maximizes availability.

1. Web/Presentation Tier
Purpose: This tier is responsible for serving the user-facing components of the application, such as web pages, images, and other static content. It also handles incoming HTTP/HTTPS requests from users.

2. Application Tier
Purpose: This tier contains the core logic of the application, processing requests and executing business logic. It acts as the intermediary between the web tier and the data tier.

3. Data Tier
Purpose: This tier manages the storage, retrieval, and management of application data. It ensures data persistence and provides secure access to data for the application tier.

# Services Used
* Amazon VPC: For creating a logically isolated network for your application.
* Amazon EC2: For hosting the web and application servers.
* Elastic Load Balancing: For distributing traffic across multiple instances.
* Amazon RDS: For managing the database.
* Amazon CloudWatch: For monitoring and logging.
* IAM: For managing access permissions and security policies.






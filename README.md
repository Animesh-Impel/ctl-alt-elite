# Ctrl+Alt+Elite - O'Reilly Architectural Katas: Fall 2024


Hello! We are the Ctrl+Alt+Elite team hailing from Bangalore, India, and we are here to present our solution for the O'Reilly Architectural Katas: Fall 2024.

## Team Members 
[Krishnaraj Ramakrishna](https://www.linkedin.com/in/krishnaraj-vr-8869b45/)  
[Raghu A M](https://www.linkedin.com/in/raghu-a-m-6381b614/)  
[Santosh Kumar](https://www.linkedin.com/in/santoshk31/)


## Contents
- [Introduction](#introduction)  
- [Requirements](#requirements)
    - [Business Requirments](#business-requirments)  
    - [Technical Requirements](#technical-requirements)
    - [Market Research](#market-research)
    - [Other Considerations](#other-considerations)
- [Architecture Characteristics](#architecture-characteristics) 
    - [Top 3 Characteristics](#top-3-characteristics)
    - [Implicit Characteristics](#implicit-characteristics)
    - [Other Characteristics](#other-characteristics)
- [Architecture Approach](#architecture-approach)
- [Use Journey](#use-journey)
    - [User experience (UX) design](#user-experience-ux-design)
- [Event Storming](#event-storming)
- [Context](#context)
    - [Complete Overview](#complete-overview)
    - [Context Diagram](#context-diagram)
- [Containers](#containers)
    - [Road Warrior System](#road-warrior-system)
- [Components](#components)
    - [API Application](#api-application)
    - [Batch Process](#batch-process)
- [Code](#code)
    - [Trip Service](#trip-api-service)
- [Deployment](#deployment)
- [ADRs](#adrs)

## Introduction


## Requirements

### Business Requirments
#### Epic-01 :: **Core System (ClearView) Module:**
- **US-01:** As the ClearView system, I want to **generate AI-based resume tips,** so that job seekers can imprtes.
- **US-02:** As the ClearView system, I want to **manage invoicing for resume unlocks,** so that recruiters are charged for unlocking candidate information.
- **US-03:**  As the ClearView system, I want to **gather metrics and analytics,** so that system performance and user behavior can be monitored and improved.ove their resumes.
- **US-04:** As the ClearView system, I want to **anonymize resumes using AI,** so that candidate privacy is maintained until employers unlock the resumes.
- **US-05:** As the ClearView system, I want to **perform candidate-job matching,** so that job seekers can find relevant opportunities and recruiters can find suitable candida

#### Epic-02 :: **User (Candidate) Module:**
- **US-06:** As a job seeker, I want to **register**, upload, and update my resume, so that I can submit it for job opportunities.
- **US-07:** As a job seeker, I want to **view matched jobs** and manage the unlocking of my resume by employers, so that I can track my job applications.
- **US-08:** As a job seeker, I want to **anonymize my resume using AI,** so that I can maintain privacy before employers unlock my full information.
- **US-09:** As a job seeker, I want to **receive AI-generated resume tips,** so that I can improve my resume to increase my chances of getting hired.

#### Epic-03 :: **HR/Recruiter Module:**
- **US-10:** As a recruiter, I want to **register and enter company information using AI,** so that I can manage job postings and candidates.
- **US-11:** As a recruiter, I want to **post and update job descriptions,** so that I can attract relevant candidates to my job listings.
- **US-12:** As a recruiter, I want to **view candidate matches,** unlock resumes, and track their hiring status, so that I can streamline the hiring process.
- **US-13:** As a recruiter, I want to **mark candidates as hired or passed,** so that I can keep track of recruitment outcomes.

#### Epic-04 :: **Admin Module:**
- **US-14:** As an admin, I want to **manage user information and internal data,** so that I can ensure system operations run smoothly.
- **US-15:** As an admin, I want to **generate analytics and reports,** so that I can provide insights on system usage and candidate-employer interactions.

### Epic-05 :: **Technical Requirements:**
- **US-16:** Richest user interface possible across all deployment platforms.
- **US-17:** Users must be able to access the system at all times (max 5 minutes per month of unplanned downtime).
- **US-18:** Response time from web (800ms) and mobile (First-contentful paint of under 1.4 sec)

## Assumptions

## Market Research

### Market Scope



## Quality Attribute Requirements
This section outlines the Quality Attribute Requirements that exert a critical influence on the overarching architecture of the software solution.
| Id | Quality Attribute | Description |
| --------- | --------- | --------- |
| QA1 | Scalability | US-16: Supports 2 million active users/week |
| QA2 | Scalability | US-17: Supports total users: 15 million (user accounts) |
| QA3 | Performance | US-03: Updates must be in the app within 5 minutes of an update (better than the competition) |
| QA4 | Performance | US-14: Travel updates must be presented in the app within 5 minutes of generation by the source.|
| QA5 | Availability | US-13: Users must be able to access the system at all times (max 5 minutes per month of unplanned downtime). |
| QA6 | Responsiveness | US-15: Response time from web (800ms) and mobile (First-contentful paint of under 1.4 sec) |
| QA7 | Interoperability | US-03: The system must interface with the agency’s existing airline, hotel, and car rental interface system |
| QA8 | Usability | US-12: Richest user interface possible across all deployment platforms. |
| QA9 | Usability | US-11: Must work internationally. |
| QA10 | Security | US-01: Poll E-Mail looking for travel-related E-Mail.  |

## Architecture Characteristics
To ensure a successful system implementation, it's vital to prioritize key architecture characteristics. These elements guarantee reliability, availability, and responsiveness, delivering a seamless user experience.


*Figure: Architecture Characteristics*

## Top 3 Characteristics
### Scalability
 Scalability allows the system to accommodate a growing user base and increased data volume, ensuring that Road Warrior can scale its services as it gains more users.
### Performance
 Performance optimization is critical to meet the specified response times and deliver real-time travel updates quickly and efficiently.
### Availability
"99.99% uptime" is a High availability, with a maximum of 5 minutes per month of unplanned downtime, is essential to ensure travelers can access their reservations and updates reliably.

## Implicit Characteristics
### Feasibility (Cost/Time)
Achieving rapid time-to-market while managing development costs is a feasible goal with the selected "mini-services" architecture.
### Security
Implementing strong authentication and authorization mechanisms is vital to safeguard traveler information and data integrity. Also storing the PII data like trip information needs to be protected and handle properly due to compliance like GDPR. 
Token-based authentication (JWT) and role-based access control (RBAC) must safeguard all API access. Additional considerations encompass encrypting data at rest and during transmission, ensuring secure credential management, effectively managing sessions, implementing refresh tokens for applications, and integrating IAM for enhanced security.
### Maintainability
Ensuring clean code, documentation, and knowledge sharing within the development team are essential for long-term system maintainability.
### Observability
Implementing comprehensive monitoring and observability solutions enables efficient tracking of system performance and early issue detection for proactive problem-solving.

## Other Characteristics

## Architecture Approach
### Architecture Style

*Figure: Architecture Style*

Based on the architecture charetrisctis we prefer to use the microservices based style.

#### Options for service granularity



### Scalability

- **Granular Scaling**: Mini-services allow for granular scaling of specific parts of the application to meet varying workloads efficiently.
- **Resource Efficiency**: Scalability ensures optimal resource usage, preventing over-provisioning and reducing operational costs.
- **Seamless Growth**: The architecture facilitates the seamless growth of the system as user numbers and data volume increase over time.

### Availability

- **Independent Deployment**: The architecture's emphasis on independent deployment contributes to high availability. If one mini-service experiences issues or requires maintenance, it does not necessarily impact the availability of other services.
- **Cluster setup with DR Plan**: All components must be capable of operating in cluster mode and accommodating horizontal scalability. Additionally, the application should be deployable in various regions to address Disaster Recovery (DR) and Business Continuity Planning (BCP) requirements, ensuring compliance with a 99.99% Service Level Agreement (SLA).
- **Robust Testing and CI/CD**: The inclusion of robust testing and CI/CD practices ensures that new updates can be quickly and reliably deployed, minimizing the likelihood of extended downtime.

### Performance

  
## Use Journey 

### User experience (UX) design
 
 #### More designs

 #### Complete walkthrough

## Event Storming

Event storming drives greater understanding and productivity by simplifying the approach and including multiple levels of stakeholders in the business. With the help of sticky notes and a willing group, you can reveal your business processes more efficiently and enjoyably.

### Identify domain events


### Connect domain events to commands


### Identify bounded context and aggregates



## Context
### Complete Overview

### Context Diagram

## Containers

## Components
### API Application



#### Workflow




## Code


## Deployment


![AWS Infrastructure Architecture](/Diagrams/aws-infra-architecture.png)
*Figure:* AWS Infrastructure Architecture  
#### Regions 
 Regions are geographic areas that contain data centers. Also helps to enable DR/BCP.  
#### Availability Zones 
Within each region, indicate the availability zones (AZs) that your resources span. AZs are physically separate data centers with redundant power, cooling, and networking.  
#### VPC (Virtual Private Cloud)  
Virtual Private Cloud(s) in use. A VPC provides a private network for your AWS resources.  
####  Subnets    
Subnets are subdivisions of your VPC and can be public or private.  
#### EC2 Instances    
EC2 instances (virtual servers) within your subnets. Specify their instance types and roles (e.g., web server, database server). 
#### RDS (Relational Database Service)    
PostgreSQL used as database engines, storage, and replication if applicable. 
Can enable read replica and table partition for higher scalablity   
#### Amazon Elastic MapReduce (EMR)    
It simplifies the process of processing and analyzing vast amounts of data using popular frameworks like Apache Hadoop, Apache Spark, Apache Flink, Apache Hive, Apache HBase, and more.
We use combination of Flink and EMR for batch processing
#### AWS Amplify   
Simplifies the process of building full-stack web and mobile applications.
It provides developers with a set of libraries, a command-line interface (CLI), and a set of back-end services to streamline the development and deployment of cloud-powered applications.  
#### S3 Buckets  
Represent Amazon S3 buckets for object storage. 
Indicate if they are used for static assets, backups, or other purposes.  
 Additionally, S3 serves as a repository for batch process job details and processed data. 
 It can also function as a data lake, housing report data and trip data for future analytical purposes.
#### Application Load Balancers  
Application Load Balancers for distributing incoming traffic across multiple instances or containers. 
Our Krakend API Gatway uses ALB for providing public access  
 
#### CloudWatch and Metrics 
Include CloudWatch for monitoring and metrics collection. Show how it integrates with other services.  

## ADRs




## Glossary
- **AWS** - Amazon Web Services
- **EKS** - Elastic Kubernets Cluster
- **EMR** - Elastic Map Reduce
- **S3** - Simple Storage Service
- **B2B** - Business to Business
- **Agencies** - Refering to Onlnie Travel Agencies (OTA)
  
## References
- 



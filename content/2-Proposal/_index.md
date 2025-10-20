---
title: "Proposal"
date: "2025-10-10"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---
{{% notice warning %}}
⚠️ **Note:** The information below is for reference purposes only. Please **do not copy verbatim** for your report, including this warning.
{{% /notice %}}

In this section, you need to summarize the contents of the workshop that you **plan** to conduct.

# Travel Journal
## A Unified AWS Serverless Solution for Travel Journal


### 1. Executive Summary
Travel Journal Web was created to help people preserve their life journeys — not only the trips they take but also the memories, emotions, and stories behind each photo. The application connects people to their experiences, turning every journey into part of their own “memory map.”

Users can upload photos, add location notes, and the system automatically recognizes the scene type (beach, mountain, city, etc.) using Amazon Rekognition. Travel routes are displayed visually and in real-time on an interactive map powered by Amazon Location Service, delivering a vivid and engaging experience.

The platform leverages the power of AWS Serverless Architecture — including Lambda, API Gateway, S3, DynamoDB, and Cognito — ensuring high performance, strong security, and scalable flexibility at an optimized cost.

### 2. Problem Statement
### What’s the Problem?
Many travel enthusiasts want to document their journeys, yet existing platforms only allow posting scattered images or notes without an intuitive connection between emotions, photos, and actual locations. It becomes difficult to organize memories, view trips on a map, or analyze travel data such as destinations, durations, and experiences. Moreover, popular cloud storage solutions fail to personalize the user experience.

### The Solution
Travel Journal App is a web-based application built on an AWS Serverless architecture to maximize efficiency and cost-effectiveness. The system uses Amazon S3 to store travel photos and notes, combined with Amazon Rekognition to automatically classify image content (beach, mountain, city, etc.). Amazon Location Service provides interactive map visualization of user journeys.

User authentication and authorization are handled by Amazon Cognito, while AWS Lambda and Amazon API Gateway process storage, display, and analytics requests in real time. Journey data is stored and analyzed through Amazon DynamoDB and Amazon OpenSearch, enabling rapid search, filtering, and data aggregation. Amazon CloudFront delivers static assets (images, maps, and web pages) globally with low latency and high security.

### Benefits and Return on Investment
The solution allows users to easily record and share their journeys while establishing a data foundation for potential expansion into a social travel platform. With an estimated cost of only USD 14.55/month, the app can support 100–200 users without physical servers. The expected ROI period is 6–8 months, achieved by saving maintenance and storage costs.

### 3. Solution Architecture
The platform adopts an AWS Serverless and Managed Services architecture to ensure flexibility, security, and cost efficiency.
Static web content is globally distributed via Amazon CloudFront, protected by AWS WAF, and domain-managed through Amazon Route 53. User data and images are stored in Amazon S3, while AWS Lambda and Amazon API Gateway handle backend logic. Amazon Cognito manages authentication and access control.

Image recognition tasks are performed using Amazon Rekognition, and geolocation data is provided by Amazon Location Service. Travel records, user data, and posts are stored in Amazon DynamoDB, while Amazon OpenSearch Service enables advanced search and analytics. Notifications are handled through Amazon SNS. The entire system is monitored via Amazon CloudWatch and AWS X-Ray, ensuring operational stability, high performance, and scalability. The architecture is detailed below:

![Travel journal Architecture](/images/2-Proposal/proposal.jpg)


### AWS Services Used
- **Amazon Route 53**: Global domain management and routing.
- **Amazon CloudFront**: Low-latency content delivery for static and dynamic assets.
- **AWS WAF**: Protects the application from common web threats.
- **AWS Lambda**: Event-driven serverless compute for backend logic.
- **Amazon API Gateway**: Acts as the interface between the frontend and Lambda backend.
- **Amazon S3**: Stores user data, images, and activity logs
- **Amazon DynamoDB**: NoSQL database for trip records and user data, optimized for fast queries.
- **Amazon Cognito**: User authentication and authorization management.
- **Amazon Rekognition**: Image analysis and labeling.
- **Amazon Location Service**: Geolocation and map visualization.
- **Amazon OpenSearch Service**: Provides advanced search and data analytics.
- **Amazon SNS**: Sends notifications to users and administrators.
- **Amazon CloudWatch**: Logs, metrics, and performance monitoring.
- **AWS X-Ray**: Traces request flows in the serverless environment.
- **AWS IAM**: Manages access roles and permissions for AWS services.
- **AWS Secrets Manager**: Securely stores and encrypts confidential credentials.
- **AWS Certificate Manager**: Issues and manages SSL/TLS certificates for secure endpoints.
- **AWS Config**: Monitors configuration changes and ensures security compliance.

### Component Design
- **User Authentication**: Managed by Amazon Cognito for login, token management, and access control.
- **Application Logic**: AWS Lambda handles travel data submissions, image uploads, and analytics requests from API Gateway.
- **Data Management**: Amazon DynamoDB stores journey details; OpenSearch provides fast indexing and search.
- **Image Analysis**: Amazon Rekognition automatically labels and classifies photo content.
- **Maps & Location Data**: Amazon Location Service tracks and displays GPS data on interactive maps.
- **Storage**: Amazon S3 stores photos, notes, and user data with event triggers for Lambda.
- **Monitoring & Notifications**: CloudWatch tracks logs and metrics, AWS X-Ray traces requests, SNS sends alerts and user notifications.
- **Content Delivery & Security**: CloudFront delivers assets, WAF protects the edge layer, and Route 53 handles DNS routing.

### 4. Technical Implementation
**Implementation Phases**
The project is divided into two main areas — web application development and AWS infrastructure integration — across three stages:
- Requirement Analysis & Architecture Design: Identify suitable AWS services (CloudFront, WAF, Cognito, DynamoDB, Lambda, API Gateway, S3, etc.) and design the overall architecture (Month 1).
- Cost Estimation & System Simulation: Calculate costs using AWS Pricing Calculator, test image and location processing workflows, and optimize system resources (Month 2).
- Development, Testing & Deployment: Build the web application, integrate AWS SDKs, test WAF protection, and monitor operations using CloudWatch and X-Ray (Month 3).

**Technical Requirements**
- Frontend: Built with React.js, deployed as static files on Amazon S3, and globally distributed via CloudFront for fast load times and reduced backend load.
- Security & Access: Protected by AWS WAF; authentication handled through Amazon Cognito (email, OAuth2).
- Backend: API Gateway routes user requests to AWS Lambda, which executes business logic such as trip logging, image uploads, and data queries.
- Database & Search: Amazon DynamoDB stores user journeys and notes; OpenSearch Service provides indexing and fast search.
- Image Analysis: Amazon Rekognition detects scenes, faces, and auto-labels photos.
- Geolocation & Maps: Amazon Location Service visualizes GPS coordinates on an interactive map.
- Monitoring: CloudWatch collects logs; AWS X-Ray traces request flows for performance tuning.
- Secrets & Certificates: AWS Secrets Manager and AWS Certificate Manager secure credentials and SSL/TLS certificates.
- Notifications: Amazon SNS sends alerts for errors or new user activities.

### 5. Timeline & Milestones
**Project Timeline**
- Internship (Months 1-3): 3 months.
    - Month 1: Learn AWS fundamentals.
    - Month 2: Design architecture, estimate costs, and refine infrastructure.
    - Month 3: Implement, test, and deploy the application.
- Post-Launch:Continue system research and improvements over the following year.
### 6. Budget Estimation
You can find the budget estimation on the [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=3ac723f9e3e9041dfee17905f76cb7fd985f771d) 

### Infrastructure Costs
- AWS Services:
    - AWS Lambda: $0.01/month
    - Amazon S3: $0.13/month
    - Amazon CloudFront: $0.61/month
    - Amazon API Gateway: $0.42/month
    - Amazon DynamoDB: $0.65/month
    - Amazon Rekognition: $0.65/month
    - Amazon Location Service: $0.60/month
    - Amazon Cognito: $0.00/month
    - Amazon SNS: $0.00/month
    - Amazon CloudWatch: $1.00/month
    - AWS X-Ray: $0.00/month
    - Amazon OpenSearch: $1.82/month
    - Amazon Route 53: $0.51/month

Total: $7.30/month, or $87.60/year


### 7. Risk Assessment
#### Risk Matrix
- Security breach or user access loss: High impact, very low probability.
- Cost increase due to Rekognition usage: High impact, medium probability.
- GPS data inconsistency: High impact, low probability

#### Mitigation Strategies
- Network: Use CloudFront for global caching and stable performance across regions.
- Infrastructure: Leverage Lambda’s automatic retry mechanism and browser caching to minimize downtime.
- Security: Apply multi-layer authentication via Cognito and strict IAM/S3 permissions.
- Cost: Set budget alerts in AWS Budgets, and optimize Lambda/S3 usage based on access patterns.

#### Contingency Plans
- Integrate SNS and CloudWatch Alerts to notify admins immediately of failures (e.g., Lambda errors, API overloads, budget overruns).
- Use CloudFormation for rapid infrastructure recovery
- Enable S3 Versioning to preserve image and log backups.

### 8. Expected Outcomes
#### Technical Improvements: 
The app automates storage, analysis, and visualization of travel data on a map, eliminating manual note-taking.
#### Long-term Value
Builds a rich dataset of travel routes, photos, and emotions — forming a foundation for future applications like personalized travel recommendations and experience analytics.
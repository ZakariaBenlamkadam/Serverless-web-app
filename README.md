# System Architecture

## Overview

### Global Architecture Diagram
The system's architecture demonstrates the flow of data between components, as illustrated in the diagram below:

![Global Architecture Diagram](/images/Lauch a serverles app.png)

### Components
- **Frontend:** Hosted on AWS S3 and delivered through Amazon CloudFront. CloudFront caches static content (HTML, CSS, JavaScript, etc.) at edge locations, ensuring faster load times and improved global performance.
- **API Gateway:** Manages incoming HTTP requests.
- **Lambda:** Executes business logic and interacts with DynamoDB.
- **DynamoDB:** Efficiently stores and retrieves application data.

---

## Explanation of the Main Components

### Frontend
The frontend consists of static files (HTML, CSS, JavaScript) hosted in an S3 bucket and delivered through Amazon CloudFront for global accessibility. 

- **S3:** Hosts the application files.
- **CloudFront:** Distributes static content globally, caching it at edge locations to reduce latency and improve load times for users. 

#### Benefits:
- Automatic scalability.
- Cost efficiency, with charges based on storage and data transfer.
- Faster access for global users due to reduced latency.

---

### API Gateway
The API Gateway serves as the entry point for HTTP requests from the frontend.

- **Purpose:** Routes requests to Lambda functions based on HTTP methods (GET, POST, PUT, DELETE).

#### Benefits:
- Provides secure communication.
- Includes request validation and monitoring features.

---

### Lambda
Lambda functions handle the application's backend logic.

- **Role:** Executes tasks such as validating inputs and interacting with DynamoDB.
- **Trigger:** Invoked by requests routed through the API Gateway.

#### Benefits:
- Pay-per-use model.
- Automatic scaling and high availability.

---

### DynamoDB
DynamoDB is a NoSQL database used for storing and retrieving application data.

- **Role:** Efficiently stores application data, such as student records.

#### Features:
- High throughput and low latency for large datasets.
- Automatic scaling and encryption at rest for security.

---

## Role of Each Component

### S3 and CloudFront: Hosting the Application
- S3 stores the static files (HTML, CSS, JavaScript).
- CloudFront ensures high availability and low latency by caching static content globally and serving it to users efficiently.

#### Benefits:
- Reduces latency and speeds up global content delivery.

---

### API Gateway: Managing HTTP Requests
- Acts as the interface between the frontend and backend.
- Routes requests to Lambda functions based on HTTP methods.

#### Benefits:
- Enhances security and monitoring for HTTP communications.

---

### Lambda: Executing Backend Code
- Executes application logic, triggered by API Gateway requests.

#### Benefits:
- Cost-effective with a pay-per-use model.
- Automatically scales based on workload.

---

### DynamoDB: Storing Data
- Provides a scalable solution for storing application data.

#### Features:
- High performance with low latency.
- Built-in security through encryption.

---

## Diagram
Refer to the architecture diagram for a visual representation of the system's components and data flow:

![Global Architecture Diagram](Lauch%20a%20serverles%20app.png)

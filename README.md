# bwm-planning

## Overview infrastructure
Indata flow:
1. Indata from external AWS account uploaded to S3.
2. Either the S3 bucket triggers the lambda directly and the calculation lambda reads data from S3, or we use a SQS queue in between. Depends on the project requirements.
3. The calculation lambda reads the incomming data from the S3 bucket and performs the necessary calculations. It will interact with RDS to fetch some data required for calculations.
4. The calculation lamda will write the results to Core View.

File upload flow:
1. Files will be uploaded to S3 (commission matrix and sales targets).
2. This will trigger the parsing labmda that will parses this data into RDS.

![Initial draft of architecture](overview.png)


## Time estimation

### 1. Requirement Gathering and Analysis

- **Duration:** 1-2 weeks
- **Activities:**
  - Define and document the project scope.
  - Understand the data formats, security requirements, and compliance needs.
  - Understand the scalability/throughput needs of the product.
  - Indentify AWS components and external integrations (e.g. Core View).
  - Pick tools to use that suit these needs.
- **Output:** A detailed requirement document.

### 2. Architecture Design

- **Duration:** 2-4 weeks
- **Activities:**
  - Design the detailed architecture.
  - Database design.
  - Identify necessary AWS services and how they will interact.
  - Plan for scalability, security, and compliance.
- **Output:** Architecture diagrams and service selection.


### 3. CI/CD Planning and Design

- **Duration:** Concurrent with Architecture Design - 1-2 weeks
- **Activities:** Decide on CI/CD tools, define stages of the pipeline.

### 4. Project Planning

- **Duration:** 1 week
- **Activities:**
  - Break down the project into smaller tasks or sprints.
  - Estimate time for each task based on complexity.
  - Allocate resources and set deadlines.
- **Output:** Project plan and timeline.

### 5. Development and Configuration

- **Duration:** Variable (3-7 months)
- **Factors Affecting Duration:**
  - Complexity of the calculations and data processing logic.
  - Integration complexity with Core View and other systems.
  - Responsiveness and burocracy of BMW.
  - Tool requirements of BMW (programming language, CI/CD tools etc.)
  - Custom development vs. using out-of-the-box AWS solutions.
- **Activities:**
  - Setup AWS accounts for dev, stage and prod.
  - Setup AWS environment (VPC, IAM roles, etc.).
  - Develop Lambda functions, data processing scripts, and integration points.
  - Write SQL for database schemas.
  - Configure databases, S3 buckets, and other AWS services.
- **Output:** Working AWS infrastructure.

### 6. CI/CD Implementation

- **Duration:** Concurrent with Development and Configuration - Adds an additional 1-2 months
- **Activities:** Set up source control, build CI pipelines, create CD pipelines, integrate with the AWS environments.

### 7. Testing

- **Duration:** 3-5 weeks
- **Activities:**
  - Some of these tasks will be done concurrently with development (e.g. unit tests).
  - Perform unit testing, integration testing, and system testing.
  - Test data processing logic, AWS service configurations, and Core View integration.
  (- Perform load testing to ensure scalability)
- **Output:** Test reports and a stable system.

### 8. CI/CD Testing and Optimization

   - **Duration:** Concurrent with Testing phase - Adds 1 week
   - **Activities:** Test CI/CD pipeline, optimize for performance and reliability.

### 9. Deployment

- **Duration:** 1-2 weeks
- **Activities:**
  - Deploy the solution to the production environment.
  - Perform final checks and validations.
- **Output:** Live system in production.

### 10. Post-Deployment Monitoring and Optimization

- **Duration:** Ongoing
- **Activities:**
  - Monitor system performance and stability.
  - Optimize configurations for cost, performance, and security.
- **Output:** Optimized and stable production system.
# bwm-planning

## Overview infrastructure

![Initial draft of architecture](design_2.png)

## Time estimation

### 1. Requirement Gathering and Analysis

- **Duration:** 1-2 weeks
- **Activities:**
  - Define and document the project scope.
  - Does BMW have requirement for certain tools (e.g. programming language, CI/CD)?
  - Understand the data formats, security requirements, and compliance needs.
  - Understand the scalability/throughput needs of the product.
  - Indentify AWS components and external integrations (e.g. Core View).
  - Pick tools to use that suit these needs.
- **Output:** A detailed requirement document.

### 2. Architecture Design

- **Duration:** 2-3 weeks
- **Activities:**
  - Design the detailed architecture.
  - Database design.
  - Identify structure of incomming data.
  - Flowchart for calculations lambda.
  - Flowchart for parsing lambda.
  - Identify necessary AWS services and how they will interact.
  - Plan for scalability, security, and compliance.
- **Output:** Architecture diagrams and service selection.


### 3. CI/CD Planning and Design

- **Duration:** Concurrent with Architecture Design - 1 week
- **Activities:**
  - Decide on CI/CD tools (preferably github actions).
  - Repository structure and settings.
  - Pick branching strategy.
  - Secret management.
  - Repository access control.
  - Plan automated testing.
  - Building and deployment.
- **Output:** Document for CI/CD design, configured repository.

### 4. Project Planning

- **Duration:** 1 week
- **Activities:**
  - Break down the project into smaller tasks or sprints.
  - Estimate time for each task based on complexity.
  - Allocate resources and set deadlines.
- **Output:** Project plan and timeline.

### 5. Development and Configuration

- **Duration:** Variable (2-3 months)
- **Factors Affecting Duration:**
  - Complexity of the calculations and data processing logic.
  - Integration complexity with Core View and other systems.
  - Responsiveness and burocracy of BMW.
  - Tool requirements of BMW (programming language, CI/CD tools etc.)
- **Activities:**
  - Setup AWS accounts for dev, stage and prod?
  - Setup AWS environment (VPC, IAM roles, etc.).
  - Develop Lambda functions.
  - Integrate towards Core View.
  - Write SQL for database schemas.
  - Configure RDS, S3 buckets, lambdas, SQS and other AWS services.
    - CDK?
    - Cloudformation?
- **Output:** Working AWS infrastructure.

### 6. CI/CD Implementation

- **Duration:** Concurrent with Development and Configuration - Adds an additional 2-3 weeks.
- **Activities:** Set up source control, build CI pipelines, create CD pipelines, integrate with the AWS environments.
- **Output:** Fully working CI/CD pipelines.

### 7. Testing

- **Duration:** 2-4 weeks
- **Activities:**
  - Some of these tasks will be done concurrently with development (e.g. unit tests).
  - Perform unit testing.
  - Test data processing logic, AWS service configurations, and Core View integration.
  - Test end to end flow.
  (- Perform load testing to ensure scalability)
- **Output:** High test coverage and end-to-end test (data insertion -> Coreview write).

### 8. CI/CD Testing and Optimization

   - **Duration:** Concurrent with Development - Adds 1 week
   - **Activities:** Test CI/CD pipeline, optimize for performance and reliability.

### 9. Deployment

- **Duration:** 1 week
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
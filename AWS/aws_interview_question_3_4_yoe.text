1️⃣ Core AWS Interview Questions (Must Know)
1. What is AWS?

AWS (Amazon Web Services) is a cloud computing platform by Amazon that provides on-demand infrastructure services like compute, storage, databases, networking, and more.

2. Difference between EC2 and Lambda?
EC2	Lambda
Virtual server	Serverless
You manage OS	Fully managed
Long-running apps	Event-driven execution
Pay for uptime	Pay per execution

👉 Use EC2 for full control apps.
👉 Use Lambda for event-driven workloads (e.g., APIs, triggers).

3. What is S3?

Amazon S3 is an object storage service used for:

File storage

Backups

Static website hosting

Storing logs

Important:

Buckets

Objects

Pre-signed URLs

Lifecycle policies

4. What is IAM?

AWS Identity and Access Management manages:

Users

Roles

Policies

Permissions

👉 Follow least privilege principle

5. What is VPC?

Amazon VPC allows you to create isolated networks in AWS.

Key components:

Subnets (Public/Private)

Internet Gateway

NAT Gateway

Route Tables

Security Groups

2️⃣ Backend + AWS Integration Questions
6. How would you deploy a Node.js app on AWS?

Options:

EC2 + PM2

Docker + ECS

Elastic Beanstalk

Lambda + API Gateway

You can mention:

CI/CD using GitHub Actions

Store environment variables in Parameter Store

Use IAM roles instead of storing credentials

7. How do you connect MongoDB/MySQL in AWS?

For MySQL:

Use Amazon RDS

Enable Multi-AZ

Use read replicas for scaling

For MongoDB:

Use EC2-hosted MongoDB OR

Use Amazon DocumentDB

8. How do you secure your backend API in AWS?

Use Security Groups

Private subnets for DB

IAM roles

Use HTTPS (ACM)

API Gateway authorizers (JWT)

3️⃣ Scenario-Based Questions (High Probability)
9. Your API is slow. What will you check?

CPU usage (CloudWatch)

DB performance

Add caching (Redis / ElastiCache)

Use read replicas

Check N+1 queries

Enable autoscaling

Mention:
Amazon CloudWatch for logs & metrics.

10. How do you scale a backend app in AWS?

Load Balancer

Auto Scaling Group

Horizontal scaling

Stateless servers

Move sessions to Redis

11. How do you handle high traffic during sales?

Auto Scaling

Use CDN (CloudFront)

Caching layer

Queue-based processing (SQS)

4️⃣ DevOps & Deployment
12. What is CI/CD in AWS?

Code pushed to GitHub

Pipeline triggers

Build Docker image

Push to ECR

Deploy to ECS

Relevant services:

AWS CodePipeline

Amazon ECR

13. Blue-Green Deployment?

Two environments:

Blue (current)

Green (new)

Switch traffic after validation.

Used in:

ECS

Beanstalk

5️⃣ System Design on AWS (3–4 Year Level)
Design a scalable REST API on AWS

Architecture:

Client
↓
Route 53
↓
Load Balancer
↓
EC2 / ECS
↓
RDS
↓
ElastiCache
↓
S3 for files

Optional:

SQS for async jobs

Lambda for event processing

6️⃣ Amazon-Style Behavioral Questions

Amazon focuses on Leadership Principles.

Example questions:

Tell me about a time you handled production issues.

Describe a time you disagreed with a teammate.

How did you optimize a slow system?

Tell me about a failure.

Use STAR method:

Situation

Task

Action

Result

🔥 Bonus: Advanced Questions (If Interviewer is Senior)

Difference between Security Groups and NACL

How does IAM role assume work?

What happens when EC2 crashes?

Explain SQS vs SNS

How does Auto Scaling decide when to scale?

How do you reduce AWS bill?

🎯 How You Should Prepare (Based on Your Profile)

Since you:

Have Node.js experience

Worked with MongoDB & MySQL

Worked in event-driven architecture

You should especially master:

RDS

IAM

VPC basics

S3

EC2

Auto Scaling

CloudWatch

SQS




// LAMBDA


1️⃣ Core AWS Lambda Interview Questions
1. What is AWS Lambda?

AWS Lambda is a serverless compute service that lets you run code without managing servers.

Event-driven

Automatically scales

Pay per execution time

Supports Node.js, Python, Java, etc.

2. What is serverless?

Serverless means:

No server management

Auto scaling

Pay-per-use

Managed infrastructure

But servers still exist — AWS manages them.

3. How does Lambda work?

Flow:
Event → Lambda Trigger → Function Execution → Response

Triggers can be:

Amazon API Gateway

Amazon S3

Amazon SQS

Amazon EventBridge

Amazon DynamoDB

4. What are cold starts?

Cold start happens when:

Lambda runs for first time

No existing execution environment available

It causes delay (100ms – few seconds).

How to reduce:

Keep package small

Use Provisioned Concurrency

Avoid heavy initialization

5. What is the maximum execution time?

15 minutes per invocation

2️⃣ Lambda + Backend Architecture
6. How would you build a REST API using Lambda?

Architecture:

Client
↓
API Gateway
↓
Lambda
↓
RDS / DynamoDB

Benefits:

Auto scaling

No server management

Cost effective for low/medium traffic

7. How do you connect Lambda to RDS?

Best practice:

Use RDS Proxy

Use connection pooling carefully

Reuse DB connection outside handler

Instead of direct DB credentials, use IAM roles.

For relational DB:

Amazon RDS

8. How does Lambda scale?

Lambda:

Scales automatically

Each request gets separate execution environment

Default concurrency limit (~1000 per region, can increase)

Important concept:

Reserved Concurrency

Provisioned Concurrency

3️⃣ Performance & Monitoring
9. How do you monitor Lambda?

Use:

Amazon CloudWatch

Logs

Metrics

Alarms

Monitor:

Duration

Errors

Throttles

Concurrent executions

10. What happens if Lambda fails?

Depends on trigger:

API Gateway → Returns error to client

SQS → Retries automatically

Async invocation → Retries 2 times

You can configure:

Dead Letter Queue (SQS or SNS)

4️⃣ Security Questions
11. How do you secure Lambda?

IAM execution role

Least privilege policy

VPC for private DB access

Use environment variables securely

Use AWS Secrets Manager

12. Can Lambda access private RDS?

Yes.

Steps:

Put Lambda inside VPC

Configure private subnets

Attach Security Groups

Use NAT Gateway for internet access if needed

5️⃣ Real Interview Scenarios (Very Important)
Scenario 1:

Your Lambda is timing out frequently.

What do you check?

Execution duration

DB response time

Memory size (increase memory → increases CPU)

Infinite loops

Cold start issues

Scenario 2:

High traffic suddenly hits your API.

Lambda behavior:

Scales automatically

May hit concurrency limit

Can throttle requests

Solution:

Increase concurrency limit

Add caching layer

Use throttling in API Gateway

Scenario 3:

Lambda connecting to MySQL is exhausting connections.

Why?
Each invocation creates new DB connection.

Solution:

Use RDS Proxy

Reuse connection

Reduce concurrency

6️⃣ Advanced Lambda Questions (3–4 Year Level)
13. Difference between synchronous and asynchronous invocation?

Synchronous:

Client waits for response

Example: API Gateway

Asynchronous:

Fire and forget

Example: S3 trigger

14. What is Lambda Layers?

Used to:

Share libraries

Reduce package size

Separate dependencies

Example:
Common Node.js utilities layer.

15. When NOT to use Lambda?

Long-running jobs (>15 min)

Heavy CPU workloads

High constant traffic (EC2 cheaper)

Large monolith apps



💡 Strong Sample Answer (Use This in Interview)

"If I need to build a scalable backend API, I would use API Gateway + Lambda. For database access, I would use RDS with RDS Proxy to avoid connection exhaustion. I would monitor the function using CloudWatch metrics and configure a Dead Letter Queue for failed async invocations. To reduce cold starts, I would optimize the bundle size and consider Provisioned Concurrency for latency-sensitive APIs."

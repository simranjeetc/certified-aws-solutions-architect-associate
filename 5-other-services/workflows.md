# Workflows

## Step Functions

- Serverless visual workflow to orchestrate Lambda functions
- All the flow is represented by a JSON state machine
- Features: sequences, parallel functions, conditions, timeouts, error handlings
- Step functions can integrate with EC2, ECS, on-premise servers and API Gateway
- Maximum execution time is 1 year
- Possibility to implement human approval features
- Use cases:
    - Order fulfillment
    - Data processing
    - Web applications
    - Any other workflow

## AWS SWF - Simple Workflow Service

- Coordinate work amongst applications
- Code runs on EC2 (not serverless)
- 1 year max runtime
- Has the concept of activity step and decision step
- Has a builtin human intervention step as well
- **Step Functions is the recommended service to be used for newer applications, except**:
    - If we need external signals to intervene in the process
    - If we need child processes that return values to parent processes

## AWS WorkSpaces

- It is a managed, secure cloud desktop
- Great to eliminate management of on-premise VID (Virtual Desktop Infrastructure)
- It is on-demand, pay per usage
- It is secure, encrypted and provides network isolation
- Integrates with Microsoft Active Directory

## AWS Appsync

- Scalable API creation with GraphQL, manages diverse data sources.
- Syncs data in real-time across mobile and web apps.
- Automatically generates client code.
- Offers real-time subscriptions, offline data sync.
- Ensures fine-grained security.
- Connects with DynamoDB, Lambda, Elasticsearch, others.
- Supports dynamic content via WebSockets subscriptions.
- Allows offline interactions in mobile apps.
- Integrates with AWS IAM, Cognito for security.
- Custom resolvers in Lambda handle complex operations.
- Optimizes data transfers, specifying needed data.
- Uses AWS CloudWatch for detailed API monitoring.







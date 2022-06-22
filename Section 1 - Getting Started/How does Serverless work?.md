Write your code in fuctions, these functions (or microservices) are stateless and respond to different events.

These functions typically run in Docker-like containers, making them highly scalable.

## Pros and Cons of Serverless Computing
### Pros
- No Server Management
- Easy & Efficient Scaling
- Built-in High Availability & Fault Tolerance
- Service Integration
- No Idle Capacity (pay for what you use)

### Cons
- Vendor Lock-ins
	- Once you pick a Serverless provider, you typically are locked in (AWS, GCP, IBM Cloud, Azure, etc)
	- Exception:  Multi-provider services
- Public Cloud
	- Some usecases or industry-specific regulatory compliance may not permit public cloud usage
- Level of Control
	- You give up some degree of control by letting a provider manage infrastructure for you

## Core Serverless Services
### AWS Lambda
Launched in 2014, AWS Lambda formulated the widespread notion and adoption of "serverless computing", Lambda is the function-based microservice arm of serverless computing.
##### Lambda Function
A specific piece of code that is uploaded to Lambda.  Ran inside of a container.  Specific access control available with [[IAM]].
### API Gateway
Use it to build RESTful APIs that can call down to your Lamda Functions.
### DynamoDB
Highly-scalable high-performance NoSQL databse with response-times in microseconds.  Available with DACS, a caching service that lays on top of DynamoDB.

## Additional Serverless Services
### Amazon S3
Store and access data on the web.  Fine-grained access control.  Can also deploy static assets to interact with Lambda functions a static website.
### Amazon SNS
Simple Notification Service allows you to publish notifications and any services or software components that subscribe to these will receive the messages.
### Amazon SQS
Send and receive messages at any volume.  Publisher/Subscriber model.  Can retain messages indefinitely, or otherwise.
### AWS Step Functions
Lets you build workflows to coordinate Lambda functions to work towards a larger service application.
### Amazon Kinesis
A platform for streaming data applications.  If you need to analyze streaming data in real-time, Kinesis is a good option.
### Amazon Athena
A SQL-like query service and syntax for querying data from your S3 Database
### CloudWatch
Log storage.
### Cognito
User authentication service, integrates with OpenID providers.
### Tools and SDKs
Extra tools to help with your AWS development efforts.

# Usecases of Serverless Architecture
## Application Backends
Use serverless for the backend of mobile, web, or IoT software solutions.  Devices act as event sources that trigger the Lambda code.
Device \> API Gateway \> Lambda Function \> S3 & DynamoDB \> Back to Device
## Real-time or Streaming Data Processing
Amazon Kinesis, DynamoDB, Lambda, and S3 can be used to perform real-time data processing.  Serverless approach is a benefit here due to the variable workloads and associated scaling elasticity.

# Frameworks and CI/CD Tools for Serverless
A typical serverless application will have a number of Lamda functions and associated API endpoints.

## Frameworks
### AWS SAM
Serverless Application Model, provided by AWS

Lightweight implementation of CloudFormation, AWS SAM uses a similar template file to CloudFormation, but is simplified.
### The Serverless Framework
Popular open-source third-party framework, provided by Serverless Inc.

Similar template file to SAM, but with a Serverless Inc flavor.  Deploys to CloudFormation.

## CI/CD Tools
### AWS CodeCommit
Version/source control that provides a git-based repository.
### AWS CodeBuild
Allows you to build your Serverless Code + create/update resources automatically.
### AWS CodePipeline
Allows you to define the deployment cycle from source repo to deployment, automate the deployment pipeline.


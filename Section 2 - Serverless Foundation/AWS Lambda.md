# Event Object (Lambda Handler)
## Lambda Invocation Types
#### Synchronous
Cognito
#### Asynchronous
S3

## Lambda Event Source Types
#### Push
S3
API Gateway
#### Pull/Poll Events
DynamoDB Stream
Kinesis Stream
SQS Queue Event

# Context Object (Lambda Handler)
Context provides us with useful runtime information, like how much time is left before the function times out, request ID, associated CloudWatch logs
## Documentation
https://docs.aws.amazon.com/lambda/latest/dg/nodejs-context.html
## Properties
- functionName
- functionVersion
- functionArn
- awsRequestId
- memoryLimitInMB
- identity
- logGroupName
- logStreamName
- clientContext
## Methods
`getRemainingTimeInMillis()`

# Logging and Error Handling
## Logging to CloudWatch
`console.error`
`console.warn`
`console.log`
`console.info`

```js
exports.handler = async (event, context) => {
	const error = new Error("Random error")
	throw error;
}
```

# Limits
https://docs.aws.amazon.com/lambda/latest/dg/gettingstarted-limits.html
## Function Limits
Memory size of 128MB to 3008MB, in 64MB Increments
Ephemeral disk capacity of 512MB
Timeout of 900 seconds or 15 Minutes
Body Payload Size:  6MB for synchronous, 128KB for Async Invocations
Deployment Package Size, 50MB compressed, 250MB uncompressed
Total Package Size within a region:  75GB
1000 concurrent executions per region across all lambda functions in that region

# Billing
Subsecond billing

## Number of Requests + Compute Time = Price
1,000,000 requests/mo for free, 400,000 GB-seconds/mo

$0.20 per million requests
$0.00001667/GB-second
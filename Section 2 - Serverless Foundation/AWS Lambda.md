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


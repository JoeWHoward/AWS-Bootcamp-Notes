Continuation of [[Hello World with AWS Lambda]]

\> AWS Dashboard \> Lambda \> Create Function
#### Serverless Function
\> Author From Scratch
- Name:  getRandomMessage
- Runtime:  Node.js 6.10
- Role:  Create a custom role
	- [[IAM]] 
	- Role Name:  lambda_basic_execution_role

\> Create Function

#### Function Code
```js
var messages = [
	"Hello world!",
	"Hello Serverless",
	"My name is Joe",
	"Did I ever tell you about Long John Dean?",
	"Remember Italian Hall!"
];

exports.handler = (event, context, callback) => {
	let message = messages[Math.floor(Math.random()*5)]
	callback(null, message);
}
```

##### Event
Retrieves incoming data from triggering event
##### Context
Sets the context of the function from the execution environment
##### Callback
Handles response back to the caller

#### Configure a Test Event
\> emptyEventData \> Create

#### CloudWatch Console
Store logs pertaining to Lambda Functions
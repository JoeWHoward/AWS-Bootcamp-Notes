Root [[Hello World with AWS Lambda]]
Continuation of [[Create your first Lambda Function]]

\> Integration Request
Integration Type: Mock -> Lambda Function `getRandomMessage`

\> Assign permissions to API Gateway to invoke Lambda Function

Integration Response \> Mapping Templates \> `application/json` \> Template
Specify the mapping of input data to json response
```json
{
	"message": $input.body
}
```

##### input
Predefined AWS variable to access the response from a Lambda function


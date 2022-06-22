### Amazon API Gateway
\> New API

#### Resources
\> Create Resource
`message`

\> Create Method
GET

Integration Type:  Mock response (hardcoded, dummy response)
![[Pasted image 20220621153211.png]]

Integration Response:  \> Mapping Templates \> `application/json`
```json
{
	"message": "Hello world!"
}
```

#### Stages
\> Actions \> Deploy API \> New Stage
`test`


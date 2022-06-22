A fully-managed serverless API service from AWS.
Create API endpoints to integrate frontend apps with the backend

# QueryString and PathParameters
```js
const moment = require('moment');

const greeting = {
	"en": "Hello",
	"fr": "Bonjour",
	"hi": "Namaste",
	"es": "Hola",
	"it": "Ciao",
	"de": "Hallo",
	"ur": "Assalamo aleikum",
	"pt": "Ola"
}

exports.handler = async (event) => {
	let name = event.pathParameters.name;
	let {lang, ...info} = event.queryStringParameters;
	let message = `${greeting[lang] ? greeting[lang] : greeting['en']} ${name}`;
	let response = {
		message: message,
		info: info,
		timestamp: moment().unix()
	}

	return {
		statusCode: 200,
		body: JSON.stringify(response),
	};
}
```

### Proxy Integrations
Pass request and event context directly from API Gateway to Lambda Integration, and directly from Lambda to API Gateway response

### CORS
Actions \> Enable CORS \> Access-Control-Allow-Origin
https://test-cors.org

### Request Validation
Used to enforce particulars about the calling request, does not pass to Lambda if not passing requirements

### Request Mapping Templates
Used to transform incoming data from Request Methods in API Gateway to a format that our Lambda function is ready to accept.  Uses Apache Velocity Templating language.
https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-mapping-template-reference.html

### Response Mapping Templates

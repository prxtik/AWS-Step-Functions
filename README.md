# Serverless - Lambda based Hashing via Step Function

This project uses AWS Lambda and Step Functions to build serverless procedures from Amazon Web Services. API Gateway is used to convert Lambdas and Step functions into REST APIs. In this technique, a State Machine configured with an API gateway evaluates a choice based on input and then invokes the respective Lambda function, which performs a hashing operation on the provided input data.

## Built with:

AWS Services: State Machine, Lambda functions, API Gateway.

## API Specifications:

The following are the API specifications for the request and response bodies of the lambdas:

### API Request Body:

```JSON
{
"input": "{
  "course_uri": "<URL of My App API>/end",
  "action": "sha256|md5|bcrypt",
  "value": "<data to perform hash operation on>"
}"
"name": "ScriptExecution",
"stateMachineArn": "<State Machine ARN that you sent>"
}
```

### API Response Body:

- From Lambda Function which performs SHA-256 hashing

  ```JSON
  {
  "banner": "<Your Banner ID>",
  "result": "<hashed value>",
  "arn": "<ARN of your SHA-256 Lambda function >",
  "action": "sha256",
  "value": "<data to perform hash operation on>"
  }
  ```

- From Lambda Function which performs MD5 hashing

  ```JSON
  {
  "banner": "<Your Banner ID>",
  "result": "<hashed value>",
  "arn": "<ARN of your MD5 Lambda function>",
  "action": "md5",
  "value": "<data to perform hash operation on>"
  }
  ```

- From Lambda Function which performs Bcrypt hashing
  ```JSON
  {
  "banner": "<Your Banner ID>",
  "result": "<hashed value>",
  "arn": "<ARN of your bcrypt Lambda function >",
  "action": "bcrypt",
  "value": "<data to perform hash operation on>"
  }
  ```

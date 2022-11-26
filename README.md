# todo-aws
> A Next.js to do list web app with FastAPI, AWS SDK, DynamoDB, Lambda Function

# Screenshot
![image](https://user-images.githubusercontent.com/58461444/204088993-14895e04-f285-464c-a928-a477d5f71868.png)

# Self note for future reference

## Getting started

### Init CDK 
> cdk init --language typescript

### Shell command to activate .sh to zip
> chmod -x pkg_for_lambda.sh

> ./pkg_for_lambda.sh

### Deploy CDK
> cdk deploy

### Infra/lib/infra-stack.ts

```ts
    // Lambda function for the API
    const api = new lambda.Function(this, "API", {
      runtime: lambda.Runtime.PYTHON_3_9,
      code: lambda.Code.fromAsset("../api/lambda_function.zip"),
      handler: "todo.handler",
      environment: {
        TABLE_NAME: table.tableName,
      },
    });
```

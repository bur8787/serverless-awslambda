## Install

```
$ npm install -g serverless
```

https://www.serverless.com/framework/docs/getting-started/

## Create project


```
$ sls create --template aws-nodejs --path myService
```

After that, `myService` is created

https://www.serverless.com/framework/docs/providers/aws/examples/hello-world/node/

## Deploy to AWS lambda

```
$ sls deploy
```

## Invoke

```
$ sls invoke -f hello
{
"statusCode": 200,
"body": "{\n  \"message\": \"Go Serverless v1.0! Your function executed successfully!\",\n  \"input\": {}\n}"
}
```


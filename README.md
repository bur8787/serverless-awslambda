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

## Run locally



### install

```
$ cd myService
$ npm init -y
$ npm install serverless-offline --save-dev
```

https://github.com/dherault/serverless-offline#installation

### Add the below plugin to serverless.yaml

```
plugins:
  - serverless-offline
```

### Run

#### Run - just once

```
$ sls invoke local -f hello
```

#### Run - many times

```
$ sls offline
offline: Starting Offline: dev/us-east-1.
offline: Offline [http for lambda] listening on http://localhost:3002
offline: Function names exposed for local invocation by aws-sdk:
           * hello: myservice-dev-hello
```

#### Invoke

```
$ aws lambda invoke /dev/null \
  --endpoint-url http://localhost:3002 \
  --function-name myservice-dev-hello
```

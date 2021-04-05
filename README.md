# Serverless-Data-Engineering-Pipeline
Project 4 for IDS721. Reproduce the architecture of the [example serverless data engineering project](https://github.com/noahgift/awslambda)

## Workflow
![alt text](https://camo.githubusercontent.com/bb29cd924f9eb66730bbf7b0ed069a6ae03d2f1a/68747470733a2f2f757365722d696d616765732e67697468756275736572636f6e74656e742e636f6d2f35383739322f35353335343438332d62616537616638302d353437612d313165392d393930392d6135363231323531303635622e706e67)

- CloudWatch Events triggers the producer function every 1 minute. The producer function will read from a table with university names in DynamoDB and pass the names into SQS.
- Once SQS received any messages, the consumer function will be triggered. The consumer function will search the university names on Wikipedia and perform a sentiment analysis. For this project, I also added a key phrase detection feature.
- The results are stored in S3 bucket as csv files.

## Reference
[https://github.com/noahgift/awslambda](https://github.com/noahgift/awslambda)

# Log Test

## Setup the Cluster

follow this tutorial https://aws-otel.github.io/docs/setup/ecs/create-cluster and use the name `Container-Insight-Example`


```
aws cloudformation create-stack --stack-name Guardrail-Container-Insight-Example-us-west-2 \
    --template-body file://cloudwatchinsight.yaml \
    --parameters ParameterKey=ClusterName,ParameterValue=Container-Insight-Example \
    --capabilities CAPABILITY_NAMED_IAM \
    --region us-west-2
```

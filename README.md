# Log Test

## Setup the Cluster (manually)

follow this tutorial https://aws-otel.github.io/docs/setup/ecs/create-cluster and use the name `Container-Insight-Example`

## Create task definition and roles

```
aws cloudformation create-stack --stack-name Guardrail-Container-Insight-Example-us-west-2 \
    --template-body file://cloudwatchinsight.yaml \
    --parameters ParameterKey=ClusterName,ParameterValue=Container-Insight-Example \
    --capabilities CAPABILITY_NAMED_IAM \
    --region us-west-2
```

## Check logs

![Alt text](/img/1_cw-ec2-metrics.png?raw=true "CloudWatch metrics")

## Delete Task Definition

```
aws cloudformation delete-stack --stack-name Guardrail-Container-Insight-Example-us-west-2
```

## Delete Cluster (manually)

remove the cluster manually from the console

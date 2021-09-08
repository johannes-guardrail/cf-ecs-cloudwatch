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

### General Metrics

Cloudwatch EC2 Metrics
![Alt text](/img/1_cw-ec2-metrics.png?raw=true "CloudWatch metrics")

Cloudwatch Cluster Metrics
![Alt text](/img/2_cw-cluster-metrics.png?raw=true "CloudWatch Cluster metrics")

### Container logs

Task Definition
![Alt text](/img/3_task-definition.png?raw=true "Task definition")

View logs of task
![Alt text](/img/4_view-logs-of-task.png?raw=true "Task Logs")

Apache Logs
![Alt text](/img/5_apache-logs.png?raw=true "Apache Logs")

## Delete Task Definition

```
aws cloudformation delete-stack --stack-name Guardrail-Container-Insight-Example-us-west-2
```

## Delete Cluster (manually)

remove the cluster manually from the console

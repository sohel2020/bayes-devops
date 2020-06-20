# K8S Creattion with kops

## Prerequisites:

1. kops >= 1.15
2. S3 Bucket
3. DNS Zone

```bash
export AWS_DEFAULT_REGION=eu-central-1
export AWS_PROFILE=production
export CLUSTER_NAME=k8s.example.com
export KOPS_STATE_STORE=s3://example-bucket
kops create -f kops.yaml
kops create secret --name $CLUSTER_NAME sshpublickey admin -i k8s-production.pub
```

Preview changes to be made on AWS:

    kops --name=$CLUSTER_NAME update cluster

Actually create the cluster:

    kops --name=$CLUSTER_NAME update cluster --yes

Wait for the cluster to be ready:

    watch -n10 kops --name=$CLUSTER_NAME validate cluster
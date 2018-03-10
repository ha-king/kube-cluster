# Kubernetes via Bastion Host

## Nested CloudFormation
This nested template deploys a VPC w/ 3AZs and a bastion host from which Kops will deploy a distributed Kubernetes gossip-cluster plus proxy dashboard and monitoring
#### Ohio region only
### Installation Guide
1. <a href="https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=VPC-Kubernetes&templateURL=https://s3-us-east-2.amazonaws.com/inf-kube-setup/cfn-templates/nested-master.template" target="_blank">![Launch](./img/launch-stack.png?raw=true "Launch")</a>
1. Click **Next** to proceed with the next step of the wizard.
1. Specify a name and all parameters for the stack.
1. Click **Next** to proceed with the next step of the wizard.
1. Click **Next** to skip the **Options** step of the wizard.
1. Check the **I acknowledge that this template might cause AWS CloudFormation to create IAM resources.** checkbox.
1. Click **Create** to start the creation of the stack.
1. Wait until the stack reaches the state **CREATE_COMPLETE**
1. Copy Bastion Host public IP from the KubeStack outputs tab

#### Wait approximately 15 minutes

#### Visit public IP of Kubernetes-Bastion instance via RDP

##### Kubernetes Dashboard
![Launch](./img/kube-dash.png?raw=true "kube-dash")

##### Grafana
![Launch](./img/grafana.png?raw=true "grafana")

##### Prometheus
![Launch](./img/prometheus.png?raw=true "prometheus")

### Cleanup cluster
From bastion as root:

1. . ~/.bash_profile
1. kops delete cluster --name private.cluster.k8s.local --yes
1. Allow 5-10 minutes for teardown
1. Delete nested master CF stack

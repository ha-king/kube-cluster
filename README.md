# Kubernetes via Bastion Host

## Nested CloudFormation
This nested template deploys a VPC w/ 3AZs and a bastion host from which Kops will deploy a distributed Kubernetes cluster.
### Ohio region only
### Installation Guide
1. <a href="https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=VPC-Kubernetes&templateURL=https://s3.amazonaws.com/infascination-public-oregon/cfn-templates/nested-master.template" target="_blank">Launch Stack</a>
1. Click **Next** to proceed with the next step of the wizard.
1. Specify a name and all parameters for the stack.
1. Click **Next** to proceed with the next step of the wizard.
1. Click **Next** to skip the **Options** step of the wizard.
1. Check the **I acknowledge that this template might cause AWS CloudFormation to create IAM resources.** checkbox.
1. Click **Create** to start the creation of the stack.
1. Wait until the stack reaches the state **CREATE_COMPLETE**
1. Copy Bastion Host public IP from the KubeStack outputs tab

#### Wait approximately 10 minutes

#### Visit public IP of Kubernetes-Bastion instance via RDP

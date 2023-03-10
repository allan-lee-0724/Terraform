# Terraform
Terraform is a tool that allows for creating "Infrastructure as Code", specifically for your cloud infrastructure. We have used similar tools before (think dockerfiles, jenkinsfiles, and manifests), but all of the previous tools required some sort of cloud infrastructure to be in place before they could be used. You needed a Kubernetes controlled cluster for your manifest files to be effective, and you needs docker images created from your dockerfiles for your application to be deployed into the cluster. With Terraform, we can actually manage the state of the cloud resources that compose the cluster (the node, the vpc, and rds instances deployed within the same vpc, etc). 

## Terraform Basics
There are three main sections to any Terraform configuration (these can all be in the same file, or separated)

### Terraform Block
This is where Terraform specific information will be placed, typically you will see a "required_providers" section here: this tells Terraform what cloud providers (if any) you are working with

### Provide Block
This is where you put the configurations necessary for interacting with the cloud provider: typically this will include some sensitive information for giving Terraform permission to interact with the cloud provider

### Resource Blocks
Resources blocks are used to define individual components of a deployment: these can be things like VPCs, servers, 3rd party resources, etdc. 
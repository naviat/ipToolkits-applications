# ArgoCD - ipToolkits

![helm lint](https://github.com/naviat/ipToolkits-applications/actions/workflows/helm-lint.yml/badge.svg)
![helm lint](https://github.com/naviat/ipToolkits-applications/actions/workflows/yaml-lint.yml/badge.svg)
![helm lint](https://github.com/naviat/ipToolkits-applications/actions/workflows/json-lint.yml/badge.svg)


## Overview

This repository contains the Argo CD deployment configurations for the ipToolkits project. It includes all the necessary YAML files and Kubernetes manifests to manage and automate the deployment process of our application using Argo CD.

> [!IMPORTANT]
> Most of components were provisioned by Terraform in `infras/terraform/modules` from [ipToolkits](https://github.com/naviat/ipToolkits/tree/main/infras/terraform/modules) repo.

## Prerequisites

- Kubernetes cluster
- Argo CD installed on the cluster
- kubectl configured to interact with your cluster

## Getting Started

### Setting Up Argo CD

Ensure that Argo CD is installed and properly configured in your Kubernetes cluster. For detailed instructions, visit [Argo CD's official documentation](https://argo-cd.readthedocs.io/en/stable/).

### Application Deployment

The `apps/` directory holds the application definitions. These definitions tell Argo CD how to deploy the ipToolkits application components to the Kubernetes cluster.

### Repository Structure

```shell
.
├── apps
│  └── iptoolkits
├── environments
│  ├── deprecated
│  └── dev
└── platform-apps
   ├── argocd-updater
   └── mongodb
```

### Managing Environments

Different environments like dev and production can be managed using separate directories within `/environments`. Customize the application manifests for each environment as needed.

### Updating Applications

To update an application, modify the respective YAML file in the `/apps` directory and commit your changes. Argo CD will automatically sync these changes to the cluster.

## License

This project is licensed under the Apache License.

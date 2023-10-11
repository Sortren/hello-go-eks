# hello-go-eks

argo-root.yaml is an experimental declarative way of defining the resources on the multiple clusters using ApplicationSet
My production-ready idea would be following:
1. Additional component (as a repository) called hello-go-tf
2. The terraform should have a bootstrap branch for defining common infra, shared between the projects
3. I'd use the [ArgoCD tf module](https://registry.terraform.io/providers/oboukili/argocd/6.0.3/docs/resources/application_set) specifically ApplicationSet
4. Configuration will be similar to the provided by me in argo-root.yaml but in the tf way
5. There are two main ways of using this approach:
   1. Installing ArgoCD on the Bootstrap EKS cluster
   2. Installing ArgoCD on the one of the usable clusters such as Dev/UAT/Prod
6. I'd suggest to have a bootstrap small simple cluster to manage the other environments.

## Installation of ArgoCD 

Despite using Terraform resources to configure Argo, you need to have a running Argo on a cluster already.
The main installation process is described in [here](https://argo-cd.readthedocs.io/en/stable/getting_started/)
But as far as we're going to use a declarative GitOps approach to manage the Argo itself, we skip steps: 6 and 7.






## What is ArgoCD?

    Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes.

    ![alt text](.images/argocd-ui.gif)

## Why ArgoCD?

* Application definitions, configurations, and environments should be declarative and version controlled. 
* Application deployment and lifecycle management should be automated, auditable, and easy to understand.

## How it works?

* Argo CD follows the GitOps pattern of using Git repositories as the source of truth for defining the desired application state. 
* Kubernetes manifests can be specified in several ways:
    1. kustomize applications
    2. helm charts
    3. jsonnet files
    4. Plain directory of YAML/json manifests
* Argo CD automates the deployment of the desired application states in the specified target environments.
* Application deployments can track updates to branches, tags, or be pinned to a specific version of manifests at a Git commit.
 
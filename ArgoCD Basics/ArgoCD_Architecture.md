## ArgoCD Architecture

![alt text](.images/argocd_architecture.webp)


### Workflow

* A developer submits a Pull Request (PR) to merge new code into the master branch. The PR undergoes a peer review process to ensure code quality, correctness, and adherence to standards.

* Once the PR is approved and merged, the updated code is pushed to the master branch.

* This push event triggers a Git webhook, which notifies ArgoCD of the new changes.

* ArgoCD, upon receiving the webhook, detects the updated Kubernetes manifests in the repository and automatically synchronizes them with the target Kubernetes cluster.

### Components

#### API Server

The API server is a gRPC/REST server which exposes the API consumed by the Web UI, CLI, and CI/CD systems.

#### Repository Server

* The repository server is an internal service which maintains a local cache of the Git repository holding the application manifests.
* It is responsible for generating and returning the Kubernetes manifests when provided the following inputs:
    1. repository URL
    2. revision (commit, tag, branch)
    3. application path
    4. template specific settings: parameters, helm values.yaml

#### Application Controller

* The application controller is a Kubernetes controller which continuously monitors running applications and compares the current, live state against the desired target state.
* It is responsible for invoking any user-defined hooks for lifecycle events (PreSync, Sync, PostSync).
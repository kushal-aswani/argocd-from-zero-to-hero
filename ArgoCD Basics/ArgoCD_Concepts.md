## Core Concepts

1. **Application:** It is a custom resource definition that define the source that can be a GIT repository or a HELM chart and destination which is a Kubernetes cluster.

2. **Project:** It acts as a logical grouping of applications and helps in policy enforcement and resource segmentation.

3. **Target State:** This is the desired state of an application, as represented by files in a GIT repository.

4. **Live State:** This is the actual state of an applicaiton in a Kubernetes cluster.

5. **Sync:** This is the process of making an application to move into a target state.

6. **Health:** It denotes the health of an application which can be in OK, Degraded or Progressing state.
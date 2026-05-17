# Project

Strimops is a cloud-native self-service platform to manage Kafka resources (topics, ACLs, schemas, users) across multiple providers using GitOps. Teams provide their configurations via an abstract YAML interface that gets converted into Kafka resources.

## Architecture

The architecture consists of the following components:

* **translator**: Reads teams' YAML configurations, validates them against defined policies, and generates a single `values.yaml` file to be consumed by the Helm chart to generate custom Kubernetes CRDs.

* **strimops-helm**: Helm chart that generates custom CRDs based on the teams' configurations.

* **strimops-operator**: Kubernetes operator that watches custom CRDs and creates, deletes, or updates Kafka resources based on the provider.

## Tech Stack

* **Python**: used for the translator
* **Go**: used for the operator
* **Helm**: used to render the CRDs on a Kubernetes cluster

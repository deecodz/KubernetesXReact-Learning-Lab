# Kubernetes Manifests Documentation

This document explains the purpose and learnings from each file in the `kubernetes-files` folder of this project.

---

## 1. `namespace.yml`
**Purpose:**
- Defines a custom namespace `dummy-react-app` to logically isolate resources for this project.

**What I learned:**
- Namespaces help organize and separate resources in a Kubernetes cluster, making it easier to manage environments and avoid naming conflicts.

---

## 2. `deployment.yml`
**Purpose:**
- Deploys two replicas of the React app container in the `dummy-react-app` namespace.
- Uses security best practices (non-root, no privilege escalation, read-only filesystem).

**What I learned:**
- Deployments manage the desired state and scaling of pods.
- SecurityContext settings are important for container hardening.

---

## 3. `service.yml`
**Purpose:**
- Exposes the React app deployment via a Kubernetes Service of type `LoadBalancer`.
- Maps external port 8080 to container port 80.

**What I learned:**
- Services provide stable networking and load balancing for pods.
- The `LoadBalancer` type is useful for exposing services outside the cluster (e.g., in cloud or with Minikube tunnel).

---

## 4. `busybox.yml`
**Purpose:**
- Deploys a simple BusyBox container for testing and debugging in the default namespace.
- The container runs an infinite loop to stay alive.
- Resource requests and limits are set for CPU and memory.

**What I learned:**
- BusyBox is useful for testing networking and debugging in Kubernetes.
- Resource requests/limits help manage cluster resources and prevent overuse.

---

**Summary:**
- This simple project taught me how to organize resources with namespaces, deploy and secure applications, expose them with services, and use utility containers for testing in Kubernetes.

  ![image](https://github.com/user-attachments/assets/3b048902-11e2-4d3c-a0e1-25807376ad21)


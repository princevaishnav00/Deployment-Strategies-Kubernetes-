# Deployment Strategies in Kubernetes

## What is Deployment?

A **Deployment** in Kubernetes is an object that manages the creation and updates of application instances (Pods). It ensures that the desired number of application replicas are running and available to users.

In simple terms, deployment is the process of making an application available for users or customers to access and use.

---

## What are Deployment Strategies?

Deployment strategies are techniques used to release a new version of an application while minimizing downtime and reducing risks during updates.

These strategies define how traffic is shifted from the old version of an application to the new version.

---

## Why Do We Need Deployment Strategies?

Deployment strategies provide several benefits:

* **Zero Downtime** – Users can continue using the application during updates.
* **Faster Rollbacks** – Quickly revert to the previous stable version if issues occur.
* **Reduced Risk** – Gradually introduce changes instead of replacing everything at once.
* **Faster Time to Market** – Deliver new features and fixes more frequently.
* **Improved Reliability** – Ensure stable and predictable application updates.

---

## Types of Deployment Strategies

| Strategy       | Description                                                                   |
| -------------- | ----------------------------------------------------------------------------- |
| Recreate       | Terminates the old version completely before deploying the new version.       |
| Rolling Update | Gradually replaces old application instances with new ones.                   |
| Blue-Green     | Maintains two environments and switches traffic to the new version instantly. |
| Canary         | Releases the new version to a small subset of users before full rollout.      |

### Strategy Links

| Deployment Strategy | Documentation |
| ------------------- | ------------- |
| Recreate            | Click me      |
| Rolling Update      | Click me      |
| Blue-Green          | Click me   (./Blue-Green-deployment/)   |
| Canary              | Click me      |

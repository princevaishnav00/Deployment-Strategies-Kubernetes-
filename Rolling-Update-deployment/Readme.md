## Rolling Update Deployment Strategy
+ A rolling update in Kubernetes is a deployment strategy used to gradually replace the existing set of Pods with a new set of Pods one by one.
+ This ensures that there is no downtime during the update process as the application continues to serve requests while the update is in progress.

# How it works ?
+ Pod Creation: kubernetes creates one new pod of newer version.
+ Pod Termination: It terminates existing pods.


| Pro's | Con's |
| ------------- | ------------- |
| Version is slowly released across instances | Rollout/Rollback can take time  |
| Convenient for stateful applications | No control over traffic |

> # Note:
> This deployment strategy is suitable for UAT,QA environment. For stateful applications suitable on production environment


Architecture Diagram:  
<p align="center">
 <img src="./Images/Rolling-Update-deploy.png" alt="Alternative text" width="800">/>
</p>
---


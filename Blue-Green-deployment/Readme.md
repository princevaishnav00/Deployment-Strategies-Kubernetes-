# Blue-Green Deployment Strategy
+ Blue-Green deployment is a strategy used in Kubernetes (and other environments) to reduce downtime and risk when deploying new versions of an application.
+ It involves maintaining two separate environments, which are referred to as Blue and Green.


#  How it works ?
+ Blue Environment: This is the live environment, where the current version of your application is running.
+ Green Environment: The new version of the application is deployed to the Green environment. During this phase, there is no impact on the users accessing the Blue environment.
+ Test the Green Environment: Once the Green environment is up, it is fully tested to ensure the new version works as expected.
+ Switch traffic: After validating that the Green environment is stable, the routing of user traffic is switched from Blue to Green. Now, the Green environment becomes the live production environment, and users interact with the new version.



| Pro's | Con's |
| ------------- | ------------- |
| Instant rollout/rollback | 	Requires double the resources  |
| Avoid versioning issue, change entire cluster state in one go | Proper test of entire platform should be done before releasing to the production environment. |


## NOTE:
> This deployment strategy is suitable for Production environment.


Architecture Diagram:  
<p align="center">
 <img src="./Images/Blue-green-deploy.png" alt="Alternative text" width="800">/>
</p>
---


# Steps to implement Blue Green deployment


+ Create Namespace
```bash
kubectl create ns bluegreen
```

+ Apply the file present in the current directory with name .yaml

```bash
kubectl apply -f Blue-Deployment.yml
kubectl apply -f Green-Deployment.yml
kubectl apply -f Blue.Green-service.yml
```

+  Run the command to monitor the deployment & pods & service
```bash
kubectl get all -n bluegreen
````

+ It will deploy nginx web page (Blue environment) and apache web page (Green environment), now try to access the blue environment (nginx) web page on browser.

 URL : `http://<EC2-PUBLIC-IP>:<nodeport>`

  <img src="./Images/Nginx-Blue.png" alt="Alternative text" width="800">


+ Now, go to the Blue.Green-service.yaml manifest file and edit the service's selector field with green version.

   <img src="./Images/blue-edit.png" width="35%"/> <img src="./Images/green-edit.png" width="35%"/>

+  Apply Blue.Green-service..yml

 ```bash
kubectl apply -f Blue.Green-service..yml
````
  

   <img src="./Images/Apache-Green.png" alt="Alternative text" width="800">

+ Now, the Green environment becomes the live production environment, and users interact with the new version.
  

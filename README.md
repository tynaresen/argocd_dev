## What is Argo CD? 
Argo CD is Continuous Delivery, open-source, declarative tool specifically dedicated to Kubernetes that uses GitOps principles. Argo CD is continuously controlling applications and making sure that the live state matches the desired state. If a desired live state deviated (google the synonym) it will be automatically reposted and scale back or sync to the desired live state. Argo Cd especially will help developer teams to deploy, manage and track all applications without diving deep into Kubernetes. Argo CD can also pull any changes or updated code from a repository and apply or deploy directly to Kubernetes resources. When using Argo CD you could also specify the configuration of your application using several types of Kubernetes manifest, including YAML or JASON, Helm charts, Jsonnet, or Ksonnet applications.


### Benefits of Argo CD:
+ Argo CD is deployed into the cluster
+ Uses git as a single source of truth
+ Provides a GUI dashboard, where you can manage deployed applications 
+ Disaster recovery, meaning that in that case, you can simply point the git repo to the newly created cluster 
+ Can easily rollback, meaning that we can revert changes


### What makes Argo CD special?
+ Support for helm, jsonet, kustomize
+ A GUI great for visualizing Kubernetes resources
+ Command line interface is also available 
+	Audit trails for applications events and all API calls
+	The app of apps pattern
+	Automation via pipeline (It’s easy to update the running version)


### Requirements:
+ Kubectl (in our case k3s)
+ Helm 

## Application Deployment:
1. Need to create a config files ( application.yaml/ deployment.yaml and services.yaml), which will basically have all required configurations.
Here should be an example of application.yaml
``` 


``` 
2.	We need to deploy the application.yaml by running the command below:
`kubectl apply -f application.yaml`

Another way to do it with helm: 
1. Remove services.yaml 
2. Run the command below:
`helm install yourapplication(nginx)  ./helm  --dry-run`
3. To watch in live motion your pods to be deployed:
`kubectl get pods –watch`
4. Expose your application to port 8080 to check if its up:
`kubectl expose deployment myapp --type=LoadBalancer --port=8080`
5. To check your services:
`kubectl get services`



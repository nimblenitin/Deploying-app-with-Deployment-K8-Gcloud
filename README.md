# Deploying-app-with-Deployment-K8-Gcloud
Deploying a better version of Voting app previously deployed with Kubernetes by including Deployment to scale pods and a Load balancer to route the request.

Steps followed:

*As Root*
```

1. Create the the necessary YAML files which includes all the App components.
$ vi postgres-deployment.yml
$ vi postgres-service.yml
$ vi redis-deployment.yml
$ vi redis-service.yml
$ vi result-app-deployment.yml
$ vi result-app-service.yml
$ vi voting-app-deployment.yml
$ vi voting-app-service.yml
$ vi worker-app-deployment.yml

2. Apply the YAML file to create the Pods, Deployments and services and checkout the resources created.
$ kubectl create -f .
$ kubectl get all

3. Increase the number of to 5 for all three deployments.
$ vi voting-app-deployment.yml
$ vi worker-app-deployment
$ vi result-app-deployment.yml

$ kubectl apply -f voting-app-deployment.yml
$ kubectl apply -f result-app-deployment.yml
$ kubectl apply -f worker-app-deployment.yml

4. Checkout the deployment to see the number of Pods in Deployment
$ kubectl get deployments

5. To check out the Load balancer, open the IP address in a browser and click on the buttons to see the request being routed to differet Pods every time by Load balancer.


```
*As Root*

kubectl version // Check Kubernetes version
kubectl cluster-info // View cluster information
kubectl get all	// Retrieve information about Kubernetes Pods, Deployments, Services, and more
kubectl run [container-name] --image=[image-name] // Simple way to create a Deployment for a Pod
kubectl port-forward [pod] [ports] // Forward a port to allow external access
kubectl expose ... // Expose a port for a Deployment/Pod
kubectl create [resource] // Create a resource
kubectl apply [resource] // Create or modify  a resource
# PowerShell
Set-Alias -Name k -Value kubectl // Create alias for PowerShell
# Mac/Linux
alias k="kubectl" // Create alias for Mac/Linux shell
kubectl --help
kubectl get pods
kubectl get services

Steps to enable the UI Dashboard
kubectl apply [dashboard-yaml-url]
kubectl describe secret -n kube-system
Locate the kubernetes.io/service-account-token and copy the token 
kubectl proxy
Visit the dashboard URL and login using the token
https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard
# Running a Pod
kubectl run command
kubectl create/apply command with a yaml file

# Run the nginx:alpine container in a Pod
kubectl run [podname] --image=nginx:alpine
kubectl get pods
kubectl get all
kubectl port-forward // expose a container port externally
# Enable Pod container to be 
# called externally
				   External port
				     |	 
kubectl port-forward [name-of-pod] 8080:80
					|
				   Internal port
# Will cause pod to be recreated
kubectl delete pod [name-of-pod]

# Delete Deployment that manages the Pod
kubectl delete deployment [name-of-deployment]
k run my-nginx --image=nginx:alpine
k port-forward my-nginx 8080:80
k delete pod my-nginx

# Creating or Applying Changes to a Pod
# Perform a "trial" create and also validate the YAML
kubectl create -f file.pod.yml --dry-run --validate-true

# Create a Pod from YAML
# Will error if Pod already exists
kubectl create -f file.pod.yml

# Alternate way to create or apply changes to a 
# Pod from YAML
kubectl apply -f file.pod.yml

# Use --save-config when you want to use
# kubectl apply -f file.pod.yml

# Use --save-config when you want to use
# kubectl apply in the future
kubectl create -f file.pod.yml --save-config


# Delete Pod using YAML file that created it
kubectl delete -f file.pod.yml

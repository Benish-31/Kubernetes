# Create a Deployment
kubectl create -f file.deployment.yml

# Alternate way to create or apply changes to a 
# Deployment from YAML
kubectl apply -f file.deployment.yml

# Use --save-config when you want to use 
# kubectl apply in the future
kubectl create -f file.deployment.yml --save-config

# Getting Deployments
k get deployments

# List all Deployments and their labels
k get deployment --show-labels

# Get all Deployments with a specific label
k get deployment -l app=nginx

# Delete Deployment
k delete deployment [deployment-name]

# Scale the Deployment Pods to 5
k scale deployment [deployment-name] --replicas=5

# Scale by referencing the YAML file
k scale -f file.deployment.yml --replicas=5

spec: 
  replicas: 3
  selector:
    tier: frontend

# Scaling Pods Horizontally
# Update the YAML file or use the kubectl scale command
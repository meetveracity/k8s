# Jenkins
Instructions to insttall Jenkins into a Kubernetes cluster using the Jenkins Helm chart.
This has been tested against version 1.3.0 of the Jenkins Helm chart

## Install Jenkins with Helm by running:
 ```helm install -n jenkins stable/jenkins -f values.yaml --version 1.3.0```

## Integration with Helm
If you want to interact with Helm from a Jenkins slave container, then you will need to create a service account that has access to Helm in the `kube-system` namespace. There is an [example YAML file](jenkins-roles.yaml) that contains the role rules that are needed for this account. You can install this service account and role in your Kubernetes cluster by running `kubectl apply -f jenkins-roles.yaml`.
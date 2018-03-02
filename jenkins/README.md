## Jenkins build and setup on k8s on AWS

Install helm
Install tiller
Clone this repo
helm --namespace jenkins --name jenkins -f ./jenkins-values.yaml install stable/jenkins

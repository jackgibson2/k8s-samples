## Jenkins build and setup on k8s on AWS

Install helm, brew install helm

Update helm repo, helm repo update

Install cert-manager, helm install stable/cert-manager

Install nginx ingress controller

helm install stable/nginx-ingress --name my-nginx --set rbac.create=false

Update dns to reflect external ip of NGINX

R53 add a resource record set associating the ELB external IP of NGINX with the subdomain; jenkins.gtxcodeninja.com

Clone this repo

helm --namespace jenkins --name jenkins -f ./jenkins-values.yaml install stable/jenkins

printf $(kubectl get secret --namespace jenkins jenkins-jenkins -o jsonpath="{.data.jenkins-admin-password}" | base64 --decode) | pbcopy


Upgrade Jenkins and fix plugin issues (there alway is some)

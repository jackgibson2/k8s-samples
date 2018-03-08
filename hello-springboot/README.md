# Hello Spring Boot

A very simple Spring Boot application that will be used as the baseline to test a number of things.
* Maven Docker Builds
* Jenkins CI
* Jenkins CD to Kubernetes
* Kubernetes ConfigMap integration
* Metrics publication and collection
* Prometheus montitoring integration
* etc...

## Prerequisites
### Kube Install
KubeCtl (link here)
Minikube (link here)
AWS with KOPS (link here)
NGINX Ingress Router (link here)
Cert Manager (link here)
### 

## Building the Application

`git clone` https://github.com/jackgibson2/k8s-samples.git

`cd hello-springboot`

`mvn package`

`docker push` **_your-repo_**/hello-springboot

`kubectl apply -f namespace.yaml`

`kubectl apply -f service.yaml`

`kubectl apply -f deployment.yaml`

`kubectl apply -f ingress.yaml`


Now you will need to update DNS for your ingress routes to recognize the application; http://hello-springboot._your-domain_.com. 
In AWS, you go to R53 and create a CNAME for ELB that points to your ingress router.  Give it about 5 minutes for DNS to update and you 
should be good to go.
[![HitCount](http://hits.dwyl.io/teamtact/https://github.com/teamtact/spring-base-rest.svg)](http://hits.dwyl.io/teamtact/https://github.com/teamtact/spring-base-rest)

# spring-base-rest
Spring Boot REST Boilerplate Project

---

# How to run in Eclipse or Spring Tool Suite (STS)?
1. Just download or clone in your local spce. 
2. In Eclipse IDE, import "Existing Maven Projects" and select the location in "Root Directory"
3. Just click finish
4. After importing the project in Eclipse IDE (or STS), right click the project and then -> Run AS -> Spring Boot App
5. You should see the logs in the console.
6. Test base basic REST api in the browser: 
       http://localhost:8080/
7. You should see the json like below:
```json
{
    "one": "two", 
    "three": "four", 
    "five": "six", 
    "seven": "eight"
}
```

# Minikube & Kubernetes

## Commands (without yaml files)
kubectl run spring-base-rest --image=spring-base-rest:latest --port=8080 --image-pull-policy Never
kubectl get deployments
kubectl get pods
kubectl logs 
kubectl expose deployment spring-base-rest --type=NodePort
kubectl get services
minikube service spring-base-rest
	http://192.168.99.104:31727/
	
## Delete the current serices & deployments
kubectl delete service spring-base-rest
kubectl delete deployment spring-base-rest

## Commands (with yaml files)ß
kubectl apply -f backend-deployment.yaml
kubectl get deployments

kubectl get deployment spring-base-rest
kubectl apply -f backend-service.yaml
kubectl get services
minikube service spring-base-rest-service

## Delete all deployements & services
kubectl delete service spring-base-rest-service
kubectl delete deployment spring-base-rest
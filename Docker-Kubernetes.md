##### Overviews
https://dev.to/sendilkumarn/kubernetes-for-everyone-opb   
https://github.com/Tkanos/minikube_kubernetes_tutorial   

##### Training
https://kubernetes.academy/ 
https://kubernetesbyexample.com/   

##### Best Practices
https://snyk.io/blog/best-practices-to-build-java-containers-with-docker/   


##### Developing java app with docker and K8s
https://www.oreilly.com/ideas/how-to-manage-docker-containers-in-kubernetes-with-java  
https://www.3pillarglobal.com/insights/building-a-microservice-architecture-with-spring-boot-and-docker-part-i  
https://www.3pillarglobal.com/insights/building-a-microservice-architecture-with-spring-boot-and-docker-part-ii  
https://www.3pillarglobal.com/insights/building-a-microservice-architecture-with-spring-boot-and-docker-part-iii  
https://www.3pillarglobal.com/insights/building-a-microservice-architecture-with-spring-boot-and-docker-part-iv  
https://stackify.com/guide-docker-java  
https://semaphoreci.com/community/tutorials/build-and-deploy-a-java-web-application-with-docker-and-semaphore  
https://microservices-demo.github.io/deployment/kubernetes-minikube.html (microservices in k8s)  
https://lernentec.com/post/running-simple-elasticsearch-kibana-minikube/  
https://www.callicoder.com/spring-boot-docker-example/ (java build docker)  
https://dzone.com/articles/quick-guide-to-microservices-with-kubernetes-sprin   

##### 

##### Running Docker images on K8s minikube instead
https://dzone.com/articles/running-local-docker-images-in-kubernetes-1   
https://medium.com/@maumribeiro/running-your-own-docker-images-in-minikube-for-windows-ea7383d931f6   
https://rominirani.com/tutorial-getting-started-with-kubernetes-on-your-windows-laptop-with-minikube-3269b54a226#.3jo76q2mx   



##### Shared memory between containers
https://docs.docker.com/engine/reference/run/#ipc-settings---ipc

##### Scaling elasticsearch with Kubernetes
https://medium.appbase.io/scaling-an-elasticsearch-cluster-with-kubernetes-120991de1451  
https://medium.appbase.io/deploy-elasticsearch-with-kubernetes-on-aws-in-10-steps-7913b607abda  
https://www.awsfeed.com/2019/05/15/running-open-distro-for-elasticsearch-on-kubernetes  
https://vocon-it.com/2019/03/04/kubernetes-9-installing-elasticsearch-using-helm-charts  


##### Storing configuration and secrets in docker and K8s
https://medium.com/google-cloud/kubernetes-configmaps-and-secrets-68d061f7ab5b (part 1)  
https://medium.com/google-cloud/kubernetes-configmaps-and-secrets-part-2-3dc37111f0dc (part 2)  
https://medium.com/@xcoulon/deploying-your-first-web-app-on-minikube-6e98d2884b3a  
https://medium.com/@xcoulon/managing-pod-configuration-using-configmaps-and-secrets-in-kubernetes-93a2de9449be  
https://medium.com/@xcoulon/storing-data-into-persistent-volumes-on-kubernetes-fb155da16666  

##### Kafka with K8s
https://portworx.com/run-ha-kafka-amazon-elastic-container-service-kubernetes/  
https://blog.kubernauts.io/apache-kafka-on-kubernetes-4425e18daba5  
https://www.youtube.com/watch?v=hB6BrhFZs5k  

##### Logging 
https://www.monitis.com/blog/containers-5-docker-logging-best-practices/  
https://logdna.com/blog/docker-logs/

##### Local Persistent Volumes
https://vocon-it.com/2018/12/20/kubernetes-local-persistent-volumes  
https://medium.com/@dfrnascimento/encryption-of-kubernetes-persistent-local-volumes-70da62e0ed68 

##### ElasticSearch with K8s
https://code972.com/blog/2019/04/117-running-elasticsearch-on-kubernetes   


##### Debugging
Running a pod in K8s and running a command in the cluster
```bash
kubectl run curl-debug-march --image=radial/busyboxplus:curl -i --tty --rm --generator=run-pod/v1
```

Useful Commands:
```shell
kubectl -n <namespace-name> describe pod <pod name>

kubectl -n <namespace-name> logs -p  <pod name> 

# To find all containers in a pod
kubectl describe pod/sas-crunchy-data-postgres-99c48fdb-pc47l -n d25862

# Output json based on depth -- eg. delete contents that are three level deep
kubectl get pod/sas-crunchy-data-postgres-99c48fdb-pc47l -n d25862 -o json | jq  'del(.[]?[]?[]?)'

# To bash into a container using k8s
kubectl exec -it sas-crunchy-data-postgres-99c48fdb-pc47l -c database -- /bin/sh

# To delete a namespace
kubectl delete ns developer


```

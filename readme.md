##########################
# First scenarious BIS
##########################
//Build image
docker build --progress=plain --no-cache -t helloworld-webserver:1.0.0 docker/

kubectl apply -f deployment-1.yaml 
kubectl get pod
kubectl port-forward helloworld-deployment-1-<nnnnnn>  8080:8080

##########################
# Second scenarious BIS
##########################
//Build image
docker build --progress=plain --no-cache -f docker/Dockerfile.getcontent -t get-content:1.0.0 docker/

kubectl apply -f deployment-2.yaml 
kubectl get pod
kubectl port-forward helloworld-deployment-2-<nnnnnn>  8080:8080

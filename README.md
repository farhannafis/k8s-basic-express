# Kubernetes with Express

## Create Docker Container

This docker container runs a basic Express server at port 3000. The dependencies are installed using ```pnpm``` package manager.

### Build docker image

```bash
docker build -t <image_name> .
```

Notes:
1. ```--t``` - Name and optionally a tag in the name:tag format

### Run a container to test the image

```bash
docker run --rm -d -p <desired_port>:<express_port> <image_name>
```

Notes:
1. ```--rm``` - Automatically remove the container when it exits
2. ```-d``` - Make the container runs in the background and print the container ID
3. ```-p``` - Publish a container's port(s) to the host

### To view running containers

```bash
docker ps
```

### To stop a specific container from running

```bash
docker stop <container_id>
```

### To push image to Docker hub

```bash
docker push <docker_hub_username>/<image_name>:<tag>
```

Note: 
1. Make sure you run ```docker login``` first before perform the ```docker push``` command
2. If no ```:<tag>``` defined, the tag defaults to ```latest```

## Create Kubernetes Cluster

## Requirement

1. Minikube
2. kubectl

## Create Kubernetes Deployment and Service definition

Refer ```kube/deployment-service.yaml```

## Start Minikube

```bash
minikube start
```

## Create Deployment and Service on Kubernetes cluster

```bash
kubectl apply -f kube/deployment-service.yaml
```

## Check components created in Kubernetes cluster

```bash
kubectl get all
```

## Run Kubernetes cluster

1. Get the service name using the command below. In this repo case is ```basic-express-k8s-service```

```bash
kubectl get svc
```

2. Then, run the minikube command as below:

```bash
minikube service <service_name>
```

## References:

1. https://www.digitalocean.com/community/tech-talks/how-to-deploy-a-resilient-node-js-application-on-kubernetes-from-scratch
2. https://www.tomray.dev/nestjs-docker-production
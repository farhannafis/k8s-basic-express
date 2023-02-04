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

## References:

1. https://www.digitalocean.com/community/tech-talks/how-to-deploy-a-resilient-node-js-application-on-kubernetes-from-scratch
2. https://www.tomray.dev/nestjs-docker-production
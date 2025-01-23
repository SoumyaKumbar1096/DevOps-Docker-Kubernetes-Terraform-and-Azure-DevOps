# Start DevOps with Docker
## 1. DevOps, Docker and Containerization
  - As per Docker docs: "Docker is used to develop, ship, and run applications within lightweight containers. This approach allows developers to separate their applications from their business infrastructure, giving them the power to deliver better code more quickly."
  - The basic components of Docker include:
  Docker images: Docker images are the blueprints for your containers. They are read-only templates that contain the instructions for creating a Docker container. You can think of a container image as a snapshot of a specific state of your application.
  
  Containers: Containers are the instances of Docker images. They are lightweight and portable, encapsulating your application along with its dependencies. Containers can be created, started, stopped, moved, and deleted using simple Docker commands.
  
  Dockerfiles: A Dockerfile is a text document containing a series of instructions on how to build a Docker image. It includes commands for specifying the base image, copying files, installing dependencies, and setting up the environment. 
  
  Docker Engine: Docker Engine is the core component of Docker. It’s a client-server application that includes a server with a long-running daemon process, APIs for interacting with the daemon, and a CLI client.
  
  Docker Desktop: Docker Desktop is a commercial product sold and supported by Docker, Inc. It includes the Docker Engine and other open source components, proprietary components, and features like an intuitive GUI, synchronized file shares, access to cloud resources, debugging features, native host integration, governance, security features, and administrative settings management. 
  
  Docker Hub: Docker Hub is a public registry where you can store and share Docker images. It serves as a central place to find official Docker images and user-contributed images. You can also use Docker Hub to automate your workflows by connecting it to your CI/CD pipelines.

  More about DevOps, Docker and Containerization, [Click here](https://www.docker.com/blog/docker-for-devops/#:~:text=Docker%20is%20used%20to%20develop,deliver%20better%20code%20more%20quickly)

## 2. Install and introduction
Installation guide from official Docker documentation: [Click here](https://docs.docker.com/engine/install/)

## 3. Important Docker Concepts: Registry, Repository, Tag, Image, Conta
  1. Registry: A Docker registry is a system for versioning, storing and distributing Docker images.
  2. Docker Hub: DockerHub is a hosted registry used by default when installing the Docker engine, but there are other hosted registries available for public use such as AWS and Google's own registries.
  3. Docker Repository: A Docker Hub repository is a collection of container images, enabling you to store, manage, and share Docker images publicly or privately. Each repository serves as a dedicated space where you can store images associated with a particular application, microservice, or project.
## 4. Docker for: Java, Javascript, Python applications
  1. Java: Image and Container
     - CMD To run a docker image: docker run -p 5000:5000 in28min/hello-world-java:0.0.1.RELEASE
     - CMD to run a docker image in detached mode: docker run -d -p 5000:5000 in28min/hello-world-java:0.0.1.RELEASE
  2. Javascript: Image and Container
     - CMD To run a docker image: docker run -p 5100:5100 in28min/hello-world-nodejs:0.0.1.RELEASE
     - CMD to run a docker image in detached mode: docker run -d -p 5100:5100 in28min/hello-world-nodejs:0.0.1.RELEASE
  3. Python: Image and Container
     - CMD To run a docker image: docker run -p 5200:5200 in28min/hello-world-python:0.0.1.RELEASE
     - CMD to run a docker image in detached mode: docker run -d -p 5200:5200 in28min/hello-world-python:0.0.1.RELEASE
   4. Rest of the commands are listed at the end of this file, [Click here](https://github.com/SoumyaKumbar1096/DevOps-Docker-Kubernetes-Terraform-and-Azure-DevOps/edit/main/Docker%20Command%20List.md#docker-command-list).   
## 5. Docker detached mode and logs
  - CMD to run a docker image in detached mode: docker run -d -p *hostport*:*dockerport* *repositorylinktoimage*
  - docker logs *imageID*
## 6. Docker Architecture
![image](https://github.com/user-attachments/assets/f5b68dbb-e5db-4bc8-ac91-790fa08c3739)

## 8. Docker Layers
 A Docker image is composed of multiple layers stacked on top of each other. Each layer represents a specific modification to the file system (inside the container), such as adding a new file or modifying an existing one.
 Link to detailed information on Docker layering, [Click here](https://docs.docker.com/get-started/docker-concepts/building-images/understanding-image-layers/)
## 9. ENTRYPOINT vs CMD
| Aspect |	ENTRYPOINT |	CMD |
| Purpose |	Defines the main command to be executed |	Provides default arguments or a default command |
| Overridability |	Not easily overridden at runtime |	Easily overridden at runtime |
| Behavior with arguments |	Arguments passed at runtime are appended |	Completely replaced by arguments at runtime |
| Default if not specified |	/bin/sh -c |	None |
| Use case |	For containers that always run the same command |	For providing default behavior that can be changed |
| Combining with the other |	Used to set the main executable |	Used to provide default arguments to ENTRYPOINT |
| Multiple declarations |	Only the last ENTRYPOINT is used |	Only the last CMD is used |
| Shell vs Exec form |	Exec form preferred (['command', 'param1']) |	Exec form preferred (['command', 'param1']) |
## 10. Docker and Microservices
  1. Running microservices as Docker containers
  2. Use Docker Link to Connect Microservices
  3. Use Custom networking to Connect Microservices
  4. Use Docker Compose to Simplify Microservices Launch
  5. More about Docker Compose

<a id="docker-cmdlist"></a>
# Docker command list

* docker --version
* docker run -p 5000:5000 in28min/hello-world-python:0.0.1.RELEASE
** docker run -p 5000:5000 in28min/hello-world-java:0.0.1.RELEASE
* docker run -p 5000:5000 in28min/hello-world-nodejs:0.0.1.RELEASE
* docker run -d -p 5000:5000 in28min/hello-world-nodejs:0.0.1.RELEASE
* docker run -d -p 5001:5000 in28min/hello-world-python:0.0.1.RELEASE
* docker logs 04e52ff9270f5810eefe1f77222852dc1461c22440d4ecd6228b5c38f09d838e
* docker logs c2ba
* docker images
* docker container ls
* docker container ls -a
* docker container stop f708b7ee1a8b
* docker run -d -p 5001:8080 in28min/hello-world-rest-api:0.0.1.RELEASE
* docker pull mysql
* docker search mysql
* docker image history in28min/hello-world-java:0.0.1.RELEASE
* docker image history 100229ba687e
* docker image inspect 100229ba687e
* docker image remove mysql
* docker image remove in28min/hello-world-java:0.0.1.RELEASE
* docker container rm 3e657ae9bd16
* docker container ls -a
* docker container pause 832
* docker container unpause 832
* docker container stop 832
* docker container inspect ff521fa58db3
* docker container prune
* docker system
* docker system df
* docker system info
* docker system prune -a
* docker top 9009722eac4d
* docker stats 9009722eac4d
* docker container run -p 5000:5000 -d -m 512m in28min/hello-world-java:0.0.1.RELEASE
* docker container run -p 5000:5000 -d -m 512m --cpu-quota=50000  in28min/hello-world-java:0.0.1.RELEASE
* docker system events
 
* docker container stats 4faca1ea914e3e4587d1d790948ec6cb8fa34f26e900c12632fd64d4722fd59a
* docker stats 42f170966ce613d2a16d7404495af7b3295e01aeb9142e1fa1762bbdc581f502
 
* cd /in28Minutes/git/devops-master-class/projects/hello-world/hello-world-python 
* docker build -t in28min/hello-world-python:0.0.2.RELEASE . 
* docker run -p 5000:5000 -d in28min/hello-world-python:0.0.2.RELEASE
* docker history e66dc383f7a0
* docker push in28min/hello-world-python:0.0.2.RELEASE
 
* cd ../hello-world-nodejs/
* docker build -t in28min/hello-world-nodejs:0.0.2.RELEASE . 
* docker container run -d -p 5000:5000 in28min/hello-world-nodejs:0.0.2.RELEASE
* docker push in28min/hello-world-nodejs:0.0.2.RELEASE
  
* cd ../hello-world-java/
* docker build -t in28min/hello-world-java:0.0.2.RELEASE . 
* docker run -d -p 5000:5000 in28min/hello-world-java:0.0.2.RELEASE
* docker push in28min/hello-world-java:0.0.2.RELEASE
  
* docker run -d -p 5001:5000 in28min/hello-world-nodejs:0.0.3.RELEASE ping google.com
 
* docker run -d -p 8000:8000 --name=currency-exchange in28min/currency-exchange:0.0.1-RELEASE
* docker run -d -p 8100:8100 --name=currency-conversion in28min/currency-conversion:0.0.1-RELEASE
  
* docker network ls
* docker network inspect bridge
  
* docker run -d -p 8100:8100 --env CURRENCY_EXCHANGE_SERVICE_HOST=http://currency-exchange --name=currency-conversion --link currency-exchange in28min/currency-conversion:0.0.1-RELEASE
  
* docker network create currency-network
* docker container stop currency-exchange
* docker container stop currency-conversion
* docker run -d -p 8000:8000 --name=currency-exchange --network=currency-network in28min/currency-exchange:0.0.1-RELEASE
* docker run -d -p 8100:8100 --env CURRENCY_EXCHANGE_SERVICE_HOST=http://currency-exchange --name=currency-conversion --network=currency-network in28min/currency-conversion:0.0.1-RELEASE
  
* docker-compose --version
* cd ../../microservices/
* docker-compose up
* docker-compose up -d
* docker container ls
* docker network ls
* docker network inspect microservices_currency-compose-network
* docker-compose down
* docker container ls -a
* docker system prune -a
* docker-compose config
* docker-compose images
* docker-compose ps
* docker-compose top
  
* docker build -t in28min/hello-world-java:0.0.1.RELEASE .
* docker push in28min/hello-world-java:0.0.1.RELEASE
  
* docker build -t in28min/hello-world-python:0.0.1.RELEASE .
* docker push in28min/hello-world-python:0.0.1.RELEASE
  
* docker build -t in28min/hello-world-nodejs:0.0.1.RELEASE .
* docker push in28min/hello-world-nodejs:0.0.1.RELEASE


1. Key Difference Between Git Fetch and Git Pull
The main difference between Git Fetch and Git Pull:

Git Fetch:

Downloads latest changes from remote repo to stores the changes in a separate branch in our local repository (local remote-tracking branches).
Does not update local working directory.
Does not cause merge conflicts.

Git Pull:

Downloads latest changes from remote repo and merges them into current branch.
Updates local working directory.
Can cause merge conflicts.
In short, git fetch is a safer and more flexible option, while git pull is faster and easier to use, but it can lead to merge conflicts.

2. Docker Registry vs Repository

Docker registry is a service that is storing your docker images.

Docker registry could be hosted by a third party, as public or private registry, like one of the following registries:

Docker Hub,
Quay,
Google Container Registry,
AWS Container Registry
or you can host the docker registry by yourself
(see https://docs.docker.com/ee/dtr/ for more details).

Docker repository is a collection of different docker images with same name, that have different tags. Tag is alphanumeric identifier of the image within a repository.

3. ADD vs CMD

The CMD command​ specifies the instruction that is to be executed when a Docker container starts
The ADD command Copy local files from the host machine into the Docker image. Download files from a remote URL and add them to the Docker image

4. 3 components of docker
Docker follows Client-Server architecture, which includes the three main components that are Docker Client, Docker Host, and Docker Registry
![image](https://github.com/Anusha2710/Intw_qns/assets/47424821/c32109a0-c9da-41e0-b859-1c1fb7e5b914)

5. Declarative vs Scripted pipeline

Declarative provides richer syntactical features over Scripted Pipeline syntax, and is designed to make writing and reading Pipeline code easier.

![image](https://github.com/Anusha2710/Intw_qns/assets/47424821/2ee1d87d-746f-4ecc-b3e2-67db3daf639c)

6. k8s yaml file

apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:1.14.2
        ports:
        - containerPort: 80
        
7. Docker file

FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000

# [What is Docker and how does it work? - YouTube](https://youtu.be/rOTqprHv1YE?t=248)
Four components of Docker:
  - Docker Client and Server: client side control from terminal, run commands to interact with server (Docker Daemon and Registry)
  - Docker Images: instructions to create Docker Containers, stored in a Dockerfile
  - Docker Containers: a standalone, executable software package which includes applications and their dependencies
  - Docker Registry: server-side service to host and distribute images, images can be stored in either public or private repositories

![Components of Docker](./Assets/Components-of-Docker.png)

Structure of Docker Engine:
![Structure of Docker](./Assets/Workflow-of-Docker.png)

Workflow of Docker:
![Workflow of Docker](./Assets/Workflow-of-Docker.png)


# Install Docker on Linux
1. set up the Docker repository
2. remove
3. download and install the Debian package


# Temporary notes
The clients and container runtime are in separate packages. Users should install and update all three packages at the same time. On Ubuntu: `$ sudo apt install docker-ce docker-ce-cli containerd.io`

[Docker Desktop vs Docker Engine?](https://www.docker.com/products/docker-desktop/alternatives/)
- Docker Desktop is for Windows and MacOS
- Docker Engine is the regular Docker for Linux

[Containerd IO vs Docker CE vs Docker CE CLI - StackOverflow](https://stackoverflow.com/questions/58741267/containerd-io-vs-docker-ce-cli-vs-docker-ce-what-are-the-differences-and-what-d)
- Docker CE (docker-ce): Docker Engine Community Edition
- Docker CE CLI (docker-ce-cli): Command Line Interface for Docker CE 
- Daemon Containerd (containerd.io): 

[How does Docker work on different OS]()
[What is Docker Daemon?]()
- Docker Daemon is a part of Docker Engine

[Docker Engine components](https://stackoverflow.com/questions/60527336/what-is-the-difference-between-docker-daemon-and-docker-engine)
- Docker Engine is the core of Docker, including its daemon (dockerd) and CLI (docker)


# References
- [Docker Overview](https://docs.docker.com/get-started/overview/)
- [Docker Get Started](https://docs.docker.com/get-started/)
- [Docker Engine release notes](https://docs.docker.com/engine/release-notes/)
- [Docker Desktop vs DIY with Docker Engine](https://www.docker.com/products/docker-desktop/alternatives/)

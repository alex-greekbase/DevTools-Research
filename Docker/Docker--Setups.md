# A glimpse of Docker: [What is Docker and how does it work? - YouTube](https://youtu.be/rOTqprHv1YE?t=248)
Four components of Docker:
  - Docker Client and Server: client side control from terminal, run commands to interact with server (Docker Daemon and Registry)
  - Docker Images: instructions to create Docker Containers, stored in a Dockerfile
  - Docker Containers: a standalone, executable software package which includes applications and their dependencies
  - Docker Registry: server-side service to host and distribute images, images can be stored in either public or private repositories

![Components of Docker](./Assets/Components-of-Docker.png)

Structure of Docker Engine:
![Structure of Docker](./Assets/Structure-of-Docker.png)

Workflow of Docker:
![Workflow of Docker](./Assets/Workflow-of-Docker.png)


# [Install Docker on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
1. uninstall old versions
    ```
    $ sudo apt-get remove docker docker-engine docker.io containerd runc
    ```
2. set up the repository
    - update the apt package index and install packages to allow apt to use a repository over HTTPS:
        ```
        $ sudo apt-get update

        $ sudo apt-get install \
            ca-certificates \
            curl \
            gnupg \
            lsb-release
        ```
    - add Docker's official GPG key:
        ```
        $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
        ```
    - set up the stable repository
        ```
        $ echo \
          "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
          $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
        ```
3. install Docker Engine
    - update apt package index and install the lateset version of Docker Engine and containerd
        ```
        $ sudo apt-get update
        $ sudo apt-get install docker-ce docker-ce-cli containerd.io
        ```
    - verify that Docker Engine is installed correctly
        ```
        $ sudo docker run hello-world
        ```

Installed packages explained
- Docker CE (docker-ce): Docker Engine Community Edition
- Docker CE CLI (docker-ce-cli): Command Line Interface for Docker CE 
- Daemon Containerd (containerd.io): container runtime

![Architecture of containers](./Assets/Containerization-Architecture.png)


# Terminologies
[Docker Engine](https://docs.docker.com/engine/)
- Docker Engine is loosely the regular Docker for Linux.
- Docker Engine is an open source containerization technolog for building and containerizing applications. Docker Engine acts as a client-server application with:
  - a server with a long-running daemon process [dockerd](https://docs.docker.com/engine/reference/commandline/dockerd/)
  - APIs which specify interfaces that programs can use to talk and talk to and instruct the Docker daemon
  - a command line interface (CLI) client [docker](https://docs.docker.com/engine/reference/commandline/cli/)

[Docker Desktop](https://docs.docker.com/desktop/)
- Docker Desktop is loosely the Windows and MacOS version of Docker Engine.
- Docker Desktop includes Docker Engine, Docker CLI client, Docker Compose, Docker Content Trust, Kubernetes, and Credential Helper [].


# References
- [Docker Overview](https://docs.docker.com/get-started/overview/)
- [Docker Engine release notes](https://docs.docker.com/engine/release-notes/)
- [Install Docker on multiple platforms](https://docs.docker.com/get-docker/)
- [Docker Desktop vs DIY with Docker Engine](https://www.docker.com/products/docker-desktop/alternatives/)

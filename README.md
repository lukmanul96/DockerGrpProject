# How To Deploy a Complete NGINX, PHP, MONGODB/MYSQL and PHPMYADMIN on your OS.

## Introduction - What is Docker ?

Docker Desktop is an easy-to-install application for your Mac or Windows environment that enables you to build and share containerized applications and microservices. Docker Desktop includes Docker Engine, Docker CLI client, Docker Compose, Docker Content Trust, Kubernetes, and Credential Helper.

Docker Desktop works with your choice of development tools and languages and gives you access to a vast library of certified images and templates in Docker Hub. This enables development teams to extend their environment to rapidly auto-build, continuously integrate, and collaborate using a secure repository.

Some of the key features of Docker Desktop include:

* Ability to containerize and share any application on any cloud platform, in multiple languages and frameworks
* Easy installation and setup of a complete Docker development environment
* Includes the latest version of Kubernetes
* Automatic updates to keep you up to date and secure
* On Windows, the ability to toggle between Linux and Windows Server environments to build applications
* Fast and reliable performance with native Windows Hyper-V virtualization
* Ability to work natively on Linux through WSL 2 on Windows machines
* Volume mounting for code and data, including file change notifications and easy access to running containers on the localhost network
* In-container development and debugging with supported IDEs


## Download and Install

* [Install Docker Desktop on Windows](https://docs.docker.com/desktop/windows/install/ "Docker Desktop Windows")
* [Install Docker Desktop on Mac](https://docs.docker.com/desktop/mac/install/ "Docker Desktop Mac")
* [Install Docker Desktop on Linux](https://docs.docker.com/desktop/linux/install/ "Docker Desktop Linux")


## Docker Dashboard

<img width="1040" alt="tutorial-in-dashboard" src="https://user-images.githubusercontent.com/79176420/174413203-9a1ae020-7d9b-4f4d-9796-8de575c662c7.png">

Docker Dashboard gives you a quick view of the containers running on your machine. The Docker Dashboard is available for Mac and Windows. It gives you quick access to container logs, lets you get a shell inside the container, and lets you easily manage container lifecycle (stop, remove, etc.).

To access the dashboard, follow the instructions in the [Docker Desktop Manual](https://docs.docker.com/desktop/dashboard/ "Docker Desktop Manual"). If you open the dashboard now, you will see this tutorial running! The container name `(jolly_bouman)` below is a randomly created name. So, you’ll most likely have a different name.

## What is a container?

Now that you’ve run a container, what is a container? Simply put, a container is a sandboxed process on your machine that is isolated from all other processes on the host machine. That isolation leverages kernel namespaces and cgroups, features that have been in Linux for a long time. Docker has worked to make these capabilities approachable and easy to use. To summarize, a container:

* is a runnable instance of an image. You can create, start, stop, move, or delete a container using the DockerAPI or CLI.
* can be run on local machines, virtual machines or deployed to the cloud.
* is portable (can be run on any OS)
* Containers are isolated from each other and run their own software, binaries, and configurations.


## What is a container image?

When running a container, it uses an isolated filesystem. This custom filesystem is provided by a container image. Since the image contains the container’s filesystem, it must contain everything needed to run an application - all dependencies, configuration, scripts, binaries, etc. The image also contains other configuration for the container, such as environment variables, a default command to run, and other metadata.

We’ll dive deeper into images later on, covering topics such as layering, best practices, and more.

### NGINX - ~~LUKMAN~~


### PHP -


### MONGODB / MYSQL - ~~JIANG~~


### PHPMYADMIN - 


**Our Teams**

| Team Members       | Matric No.           
| ------------- |:-------------:|
| Jiang Ao      | 1834913 | 
| Muhammad Asyraf bin Anahar     | 2027199|   
| Muhammad Lukmanulhakim| 2029299| 
| Anas Fuad Abdo Mohammed | 2014265| 

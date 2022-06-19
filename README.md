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

## Prerequisites
* A fresh Ubuntu 20.04 server on the Atlantic.Net Cloud Platform
* A root password configured on your server

### NGINX - ~~LUKMAN~~

## NGINX - What is NGINX?

Nginx is a powerful, advanced web server we can use to serve a variety of content, such as static web pages and APIs. In this section, we’ll begin by creating a new Dockerfile with the required instructions for building and running the Nginx image.

## Using the NGINX Open Source Docker Image

You can create an NGINX instance in a Docker container using the [NGINX Open Source Image](https://registry.hub.docker.com/_/nginx/ "NGINX Open Source Image") from Docker Hub.

Let’s start with a very simple example. To launch an instance of NGINX running in a container and using the default NGINX configuration, run this command:

`# docker run --name mynginx1 -p 80:80 -d nginx
fcd1fb01b14557c7c9d991238f2558ae2704d129cf9fb97bb4fadf673a58580d`

Break this down:

* the run sub-command specifies that we want to run the container
* the -d flag indicates that we want to run the image in detached mode
* the -p option signifies the port number in the format local-port:container-port. In this case, we are mapping port 80 in the container to port 80 on the server
* the final argument nginx specifies the tag of the image we want to run

We’re done at this point. Let’s see the status of our Docker image: ![Screenshot 2022-06-19 at 09 39 19](https://user-images.githubusercontent.com/79176420/174462339-6c945a26-a7c8-4d72-8cac-2c7d3f48318a.png)


Open your browser, then check the newly built server.

![72c10d6e-b194-45ba-9c42-d84451a74df3 (1)](https://user-images.githubusercontent.com/79176420/174462297-78087093-61fc-45d0-a38d-160b9b3c1bdc.png)



### PHP - ~~Asyraf~~

## What is PHP?
PHP is an open-source server-side scripting language that many devs use for web development. It is also a general-purpose language that you can use to make lots of projects, including Graphical User Interfaces (GUIs).

## Create a PHP Container
First, create a new directory inside your project with the following command:

`mkdir -p ~/docker-project/www/html`

Next, create an index.php file to verify your PHP version.

`nano ~/docker-project/www/html/index.php`

Add the following lines:

     `<!DOCTYPE html>  
     <head>  
      <title>Hello World!</title>
     </head>  
     <body>  
      <h1>Hello World!</h1>
      <p><?php echo 'We are running PHP, version: ' . phpversion(); ?></p>
     </body>`
     
 Save and close the file, then create a directory for Nginx inside your project directory:
 
`mkdir ~/docker-project/nginx`

Next, create an Nginx default configuration file to run your PHP application:

`nano ~/docker-project/nginx/default.conf`







### MONGODB / MYSQL - ~~JIANG~~
1.Pull MySQL image<br>
  "$ docker pull mysql:latest"
<img width="1040" src="https://user-images.githubusercontent.com/101516004/174434911-c42a9f58-92d5-4bb4-9c25-7332c4aed0a8.png">
2.Viewing a Local Mirror<br>
  "$ docker images"
<img width="1040" src="https://user-images.githubusercontent.com/101516004/174435008-cdc28c70-a059-40d6-9281-25dffe46fa45.png">
3.Run container<br>
  "$ docker run -itd --name mysql-test -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 mysql"<br>
  ("MYSQL_ROOT_PASSWORD=123456": Set the password of user root of the MySQL service)<br><br>
4.Check whether the installation is successful<br>
  "$ docker ps"
<img width="1040" src="https://user-images.githubusercontent.com/101516004/174435123-9e563178-54f3-490f-879f-559987308711.png">
  The MySQL service can be accessed from the local machine using root and password 123456
<img width="1040" src="https://www.runoob.com/wp-content/uploads/2016/06/docker-mysql7.png">

### PHPMYADMIN - Anas
 1.To test your Docker installation, open a terminal and run this command ($ docker version)
 2. to obtain a MySQL docker image, enter the following command ($ docker pull mysq1:8.0.1) 
 3. The previous command will download version 8.0.1 of mysql from the Docker store, allowing you to execute it on your local machine: $ docker run --name my-own-mysql -e MYSQL_ROOT_PASSWORD=mypass123 -d mysq1:8.0.1 
 4. If everything went well, you should be able to see the container running by typing the following command: $ docker ps -a 
 5. you can test access to the MySQL instance using the docker exec command, as seen below: $ docker exec -it my-own-mysql bash To download the most recent stable version of the picture, use a terminal and enter the following: $ docker pull phpmyadmin/phpmyadmin:latest
 6.  we need to run the container making sure that the container connects with the other container running mysql. In order to do so we type the following c. $ docker run --name my-own-phpmyadmin -d --link my-own-mysql:db -p 8081:80 phpmyadmin/phpmyadmin 
 7.  $ docker ps -a
 ![1](https://user-images.githubusercontent.com/107059995/174479430-ae7a84f9-5b24-4e66-a776-78272984352f.png)

 8.   Open your preferred browser and enter the following address: http://localhost:8081/ As a result, your instance of phpfrlyAdmin will appear. To gain acce as the login and the password you created in step one when running the mysql container. 
 ![2](https://user-images.githubusercontent.com/107059995/174479270-f2121adf-769f-45d8-bc73-36a77e3ae8cd.png)




**Our Teams**

| Team Members       | Matric No.           
| ------------- |:-------------:|
| Jiang Ao      | 1834913 | 
| Muhammad Asyraf bin Anahar     | 2027199|   
| Muhammad Lukmanulhakim| 2029299| 
| Anas Fuad Abdo Mohammed | 2014265| 

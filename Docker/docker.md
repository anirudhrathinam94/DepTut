
WHY DO WE USE DOCKER
--------------------

- Consider the case where we are trying to install a software. There is a likelihood that the following happened:
  
  - download installer
  - run installer
  - ERROR MESSAGE
  - try to troubleshoot (search google etc)
  - run installer again
  - ANOTHER ERROR

- This is what docker is trying to fix
- Docker wants to make it easy for us to install kind of software on any given computer not just on your laptop but on webservers and cloud based platforms as well

Consider the following example where we try to install redis (an in memory data store). Page says run the following:

    $ wget http://download.redis.io/releases/redis-5.0.5.tar.gz
    $ tar xzf redis-5.0.5.tar.gz
    $ cd redis-5.0.5
    $ make

We get an error saying wget command not found. 

- In this case it is easy to fix but in other cases troubleshooting might be a huge pain in the neck.
- Docker can be used to solve the above problem very easily

To run redis in docker simply run the following:

  docker run -it redis

And we have a running instance of redis

- **So why do we use docker?: Because it makes life easy and runs everything without us worrying about setup/dependencies**

WHAT IS DOCKER
---------------

- Docker is an ecosystem for creating and running containers. The ecosystem consists of:
  - Docker client
  - Docker server
  - Docker machine
  - Docker images
  - Docker hub
  - Docker compose
- These are all tools that come together to form a platform or ecosystem for running containers
- So what is a container?
  - To answer that let us consider what happened when we tried running redis
    - When I ran the command, the Docker CLI reached out to the Docker hub
    - It then downloaded a single file called an image
    - An image is a single file containing all the dependencies and all the configuration required to run a very specific program. In this case: Redis
    - The image is a single file that is stored in your HDD.
    - You can use the image to create one or more containers
  - A container is a single instance of an image.
  - You can think of it like a running program
  - It has its own isolated set of hardware resources.
    - It has its own set of memory
    - It has its own set of networking tech
    - It has its own space of HDD space etc

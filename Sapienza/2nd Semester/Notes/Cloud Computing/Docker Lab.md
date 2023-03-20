# 2.1.1 Part 1: Getting started

## Q1: Why you run the container docker/getting-started in detached mode?
Detached mode means that the container will be running in the **background**, without user interaction. This is useful because the terminal where the process was started can closed and the user can run other commands.

## Q2: What is the difference between a container and a container image?
The container image is the file that contains all of the instructions for how to **build** the container. It is the blueprint that tells docker how to create the container. Depending on you needs, there are many images available depending on your needs, e.g. a python image that comes with python already installed. The container is a **runnable instance** of the image which is managed by Docker.

# 2.1.2 Part 2: Sample application
## Q1: What is the meaning of the docker’s directives used in the docker file? Please comment on each of the directives.
## Q2: Why it is important to tag a container image?
Tagging images is important because it allows you to **identify** your image after building it. 
## Q3: Why we should bind a host port with the container port?

# 2.1.3 Part 3: Update the application
## Q1: It is possible to bind two containers on the same host port?
## Q2: Why and when, after stopping a container, you could need to remove it?
## Q3: It is possible to remove a running container, without stopping it before the removal?

# 2.1.4 Part 4: Share the application
## Q1: Given a container image available on a docker image repository, can you start an instance of the image on any docker host? Is there any limitation?

# 2.1.5 Part 5: Persist the DB
## Q1: If you run two instances of the same container image, let’s call them container A and container B, and you create a file in container A, is that new file visible in container B?

## Q2: Why in the docker command “docker run -d ubuntu bash -c "shuf -i 1-10000 -n 1 -o /data.txt && tail -f /dev/null" we need to keep the container running with “tail -f /dev/null”?
## Q3: What you can do with the “docker exec” command?
## Q4: Let assume you decide to use a volume. Why you need to mount the volume in the container file system? Does that mean you modify the container filesystem?
## Q5: In this part of the tutorial, you have created a volume. Where is the volume located in the file system of your docker host?

# 2.1.6 Part 6: Use bind mounts
## Q1: What is a dev-mode container?
## Q2: Can we run a container, install software dependencies, and then use the updated container without building first the image?

# 2.1.7 Part 7: Multi container app & Part 8: Use Docker Compose
## Q1: What is a Docker service?
## Q2: Can we spin up a single instance of a docker container using a docker-compose file?
## Q3: Can we run a MySQL container and store the database structure and data in a volume?
## Q4: Is the order of the services defined in a docker-compose file important, or is it irrelevant which service is defined first?
## Q5: Is it mandatory to define the network in a docker-compose file?
## Q6: If you would like to run a multi-container app, is it necessary to use docker compose (i.e. to define a service) or you can achieve the same objective using docker commands from the shell? Does a service offers more than just running a multiple container app with a single command?
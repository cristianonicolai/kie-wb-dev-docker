# KIE Workbench Development Docker Image

## Docker image

To allow you to quickly get started with the Kie Workbench fully integrated with a running Kie Server, a Docker image is generated as part of the build.
This image contains all three applications (Kie Workbench, Kie Server and Case Management Showcase) deployed to a single WildFly 10 instance.
It also provides all the necessary settings to retrieve the necessary data from the running Kie Server instance.
A set of pre-defined users is provided with the following credentials: admin/admin and user/user.
Please note, that you need [Docker](https://www.docker.io/) installed in your system to successfully build the demo image.
For more info regarding how to use the docker-maven-plugin, check the GitHub [documentation](https://github.com/fabric8io/docker-maven-plugin) and [User Manual](https://dmp.fabric8.io/)

To build the image, please execute the following command:
```
mvn clean install
```
Once the build is complete you can check your local Docker repository for a new image with name: jboss/kie-wb-dev-docker
```
docker images
```

To start the image and follow the logs, please execute the following command or simply use the Docker CLI
```
mvn docker:start -Ddocker.follow=true
```
The newly created container image will be started and a random port will be assigned to in your localhost to the WildFly instance running on the container.
You can check the actual value by executing:
```
docker ps
```

To stop the container and remove the image
```
mvn docker:stop
```
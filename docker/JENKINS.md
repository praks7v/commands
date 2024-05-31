# Run Jenkins as a Docker Container

## Steps

**Step 1: Pull the Jenkins Docker Image**

First, you need to pull the official Jenkins Docker image from [Docker Hub](https://hub.docker.com/r/jenkins/jenkins):

```
docker pull jenkins/jenkins:lts-jdk17
```
The `lts` tag refers to the Long-Term Support version of Jenkins, which is the most stable and recommended for production use.

**Step 2: Create a Docker Volume for Jenkins Data**

To persist Jenkins data, it's a good idea to use a Docker volume:

```
docker volume create jenkins_data
```

**Step 3: Run Jenkins Container**

Run the Jenkins container using the following command:

```
docker run -d --name jenkins -p 8080:8080 -p 50000:50000 -v jenkins_data:/var/jenkins_home jenkins/jenkins:lts-jdk17
```
Here's a breakdown of the command:

- `-d`: Run the container in detached mode.
- `--name jenkins`: Name the container jenkins.
- `-p 8080:8080`: Map port 8080 on the host to port 8080 on the container (the Jenkins web interface).
- `-p 50000:50000`: Map port 50000 on the host to port 50000 on the container (used for Jenkins agent communication).
- `-v jenkins_data:/var/jenkins_home`: Mount the Docker volume jenkins_data to the Jenkins home directory inside the container, ensuring data persistence.
- `jenkins/jenkins:lts-jdk17`: Specify the Jenkins Docker image to use.

**Step 4: Access Jenkins**

After the container is running, you can access Jenkins by navigating to `http://<your-docker-host-ip>:8080` in your web browser. If you're running Docker on your local machine, you can use http://localhost:8080.

**Step 5: Unlock Jenkins**

The first time you access Jenkins, you'll be prompted to unlock it. To find the initial admin password, run:

```
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```
Use the displayed password to unlock Jenkins.

**Step 6: Complete the Setup**

Follow the on-screen instructions to complete the Jenkins setup, which includes installing recommended plugins and setting up the first admin user.

**Optional: Running Jenkins with Docker Compose**

If you prefer to use Docker Compose for managing your Docker containers, you can create a `docker-compose.yml` file:

```yaml
version: '3.8'

services:
  jenkins:
    image: jenkins/jenkins:lts
    container_name: jenkins
    ports:
      - "8080:8080"
      - "50000:50000"
    volumes:
      - jenkins_data:/var/jenkins_home

volumes:
  jenkins_data:
```

Then, run the following commands:

```
docker-compose up -d
```
This will start Jenkins using Docker Compose.

By following these steps, you should be able to successfully run Jenkins in a Docker container and access it via your web browser.

# Using Docker Local Registry to Push Images

## Prerequisites

- Docker installed on your machine. [Install Docker](https://docs.docker.com/get-docker/)

## Steps

1. **Run a Local Docker Registry**

Start a local Docker registry container:

    docker run -d -p 5000:5000 --name registry registry:latest

2. **Tag Your Docker Image**

Tag the image you want to push to your local registry:

    
    docker tag <source-image> localhost:5000/<desired-image-name>:<tag>
    

Replace `<source-image>` with the name of your local image, `<desired-image-name>` with the name you want to give the image in your local registry, and `<tag>` with the version tag (e.g., latest).

Example:

    
    docker tag my-app:latest localhost:5000/my-app:latest
    

3. **Push the Image to the Local Registry**

Push the tagged image to your local registry:

    
    docker push localhost:5000/<desired-image-name>:<tag>


Example:

    
    docker push localhost:5000/my-app:latest


4. **Verify the Image in the Local Registry**

You can verify that the image is successfully pushed by listing the images in the registry:


    curl -X GET http://localhost:5000/v2/_catalog


To see the tags for a specific repository, use:


    curl -X GET http://localhost:5000/v2/<desired-image-name>/tags/list
    

Example:


    curl -X GET http://localhost:5000/v2/my-app/tags/list


5. **Pull the Image from the Local Registry**

To pull the image from your local registry to another machine (or the same machine), use the following command:


    docker pull localhost:5000/<desired-image-name>:<tag>
    

Example:


    docker pull localhost:5000/my-app:latest


## Full Example

Here's a full example to illustrate the process:

1. Build a Docker image:

    ```sh
    docker build -t my-app:latest .
    ```

2. Tag the Docker image:

    ```sh
    docker tag my-app:latest localhost:5000/my-app:latest
    ```

3. Push the image to the local registry:

    ```sh
    docker push localhost:5000/my-app:latest
    ```

4. Verify the image is in the registry:

    ```sh
    curl -X GET http://localhost:5000/v2/_catalog
    curl -X GET http://localhost:5000/v2/my-app/tags/list
    ```

5. Pull the image from the local registry:

    ```sh
    docker pull localhost:5000/my-app:latest
    ```

By following these steps, you can easily push and pull Docker images to and from your local Docker registry.


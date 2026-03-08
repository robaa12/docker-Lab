## CMD vs ENTRYPOINT

| Feature                     | CMD                                         | ENTRYPOINT                               |
| --------------------------- | ------------------------------------------- | ---------------------------------------- |
| **Purpose**                 | Default command / arguments                 | Fixed main executable                    |
| **Override at runtime**     | Yes — any `docker run` argument replaces it | Only with `--entrypoint` flag            |
| **Role when used together** | Provides default arguments to ENTRYPOINT    | Acts as the executable                   |
| **Use case**                | Flexible defaults that users can swap       | Container behaves like a specific binary |

## COPY vs ADD

| Feature                   | COPY                             | ADD                                     |
| ------------------------- | -------------------------------- | --------------------------------------- |
| **Purpose**               | Simple, explicit file copy       | Copy with extra powers                  |
| **Local files**           | Yes                              | Yes                                     |
| **Auto-extract archives** | No                               | Yes (`.tar`, `.tar.gz`, etc.)           |
| **Remote URLs**           | No                               | Yes (HTTP/HTTPS)                        |
| **Predictability**        | High — does exactly what it says | Lower — implicit behaviors can surprise |
| **Recommended for**       | Most cases                       | Only when extras are needed             |

## Problem 1:

- Run the container hello-world
  ![](image.png)
- Check running containers
  ![running containers](image-2.png)
- Run the stopped container again
  ![stopped container](image-3.png)
- Remove the container
  ![alt text](image-4.png)
- List All images
  ![list images](image-5.png)
- Delete image
  ![delete image](image-6.png)

## Problem 2:

- Run container ubuntu in an interactive mode
  ![alt text](1772786848238810907.png)
- Run "echo docker" inside the container
  ![alt text](image-7.png)
- Create hello-docker file
  ![alt text](image-8.png)
- Stop & remove the container
  ![alt text](1772787025862941163.png)
  **Comment about hello-docker file** :- The file is gone forever. It exists only the lifetime of the container.
- Remove all stoped containers
  ![alt text](image-9.png)

## Problem 3:

- Deploy a MySQL database called app-database. Use the mysql latest image, and use the
  -e flag to set MYSQL_ROOT_PASSWORD to P4sSw0rd0!. The container should run in the
  background.
  ![alt text](image-10.png)

## Problem 4:

- Run the image Nginx
  ![alt text](image-11.png)

- Add html static files to the container and make sure they are accessible
  ![alt text](image-12.png)
  ![](image-13.png)

- Commit the container with image name IMAGE_NAME
  ![alt text](image-14.png)

## Problem 5:

- Make simple python application
  ![alt text](image-15.png)

- Create Dockerfile for python application
  ![alt text](image-16.png)

- Build the image and test it
  ![alt text](image-17.png)
  ![alt text](image-19.png)
- Push the image to docker hub
  - Login to Docker hub
    ![alt text](image-20.png)
    ![alt text](image-21.png)
  - Tag and Push the image
    ![alt text](image-22.png)
    ## [Docker Image Link](https://hub.docker.com/r/rob3a/python-app)

---

# Lab 2

## Problem 1:

- Create the two named Volumes:-
  ![alt text](image-23.png)
- Run the first container and attach both volumes
  ![alt text](image-24.png)
- Edit HTML content inside the container
  ![alt text](image-25.png)
- Remove the original container
  ![alt text](image-26.png)
- Running two containers sharing the same volume
  ![](image-27.png)
- Verify that they see the same html volume
  ![alt text](image-28.png)

## Problem 2:

- Prepare host files
  ![alt text](image-29.png)
- Run nginx-bind-mount container
  ![alt text](image-30.png)
- Verify data is accessible
  ![alt text](image-31.png)
- Edit data on the host
  ![alt text](image-33.png)
- Files isn't deleted even when we rm the container
  ![alt text](image-34.png)
- Run a New Container — Verify Old Data Persists
  ![alt text](1772803249766603161.png)
  ![alt text](image-36.png)

---

# Lab 3 (Network)

## Step 1: Create the Two Networks

![alt text](1773000692613082915.png)

## Step 2: Create a Simple Flask App

![alt text](image-37.png)

## Step 3: Create the nginx Container (network1 only)

![alt text](image-38.png)

## Step 4: Create the Flask Container (BOTH networks)

![alt text](image-39.png)

## Step 5: Create the MariaDB Container (network2 only)

![alt text](image-40.png)

## Verification:

![alt text](1773000987599429828.png)
![alt text](1773001009583930034.png)
![](image-41.png)

---

# Lab 4 (Docker Compose)

## Step 1: Create project file structure:

![alt text](image-42.png)

## Step 2: Create Docker compose file:

![alt text](image-43.png)

## Step 3: Run Docker compose:

![alt text](image-44.png)

---

# Lab 5 (Docker Compose (Flask + redis example) )

## Step 1: Create project structure:

![alt text](image-45.png)

## Step 2: Create Docker Compose file:

![alt text](1773005554925936468.png)

## Step 3: Run Docker Compose:

![alt text](image-46.png)

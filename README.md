<h1>Table of contents</h1>

- [Section 1: Resources for this course](#section-1-resources-for-this-course)
- [Section 2: Introduction \& Installation](#section-2-introduction--installation)
  - [1. Install Docker](#1-install-docker)
  - [2. Install Docker Compose](#2-install-docker-compose)
  - [3. Download the Jenkins Docker Image](#3-download-the-jenkins-docker-image)
  - [4. Create a Docker Compose File for Jenkins](#4-create-a-docker-compose-file-for-jenkins)
  - [5. Create a Docker Container for Jenkins](#5-create-a-docker-container-for-jenkins)
  - [6. Access Jenkins](#6-access-jenkins)
- [Section 3: Getting Started with Jenkins](#section-3-getting-started-with-jenkins)
  - [1. Create Your First Jenkins Job](#1-create-your-first-jenkins-job)


## Section 1: Resources for this course

In this repo you will find all the resources that we use in the course.

https://github.com/ricardoandre97/jenkins-resources

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

## Section 2: Introduction & Installation
 
### 1. Install Docker

- Download Docker Desktop from the official website.

- Install **Docker Desktop** by following the on-screen instructions.

- Open **Docker Desktop** and **ensure it is running**.

### 2. Install Docker Compose
 
**Windows**

Docker Compose is included with **Docker Desktop**.

Verify installation:
```sh
docker-compose --version
```

### 3. Download the Jenkins Docker Image
https://hub.docker.com/r/jenkins/jenkins
```sh
docker pull jenkins/jenkins:lts
```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 4. Create a Docker Compose File for Jenkins
Create a `docker-compose.yml` file in your working directory:

```yaml
version: '3.8' # Specify the Docker Compose file format version

services:
  jenkins:
    image: jenkins/jenkins:lts
    container_name: jenkins
    ports:
      - "8080:8080"
    volumes:
      - jenkins_home_data:/var/jenkins_home # Persist Jenkins data (configs, plugins, jobs)
    networks:
      - net # Define a custom Docker network

volumes:
  jenkins_home_data: # Define a named volume for Jenkins

networks:
  net:  
    driver: bridge  # Use bridge networking mode
```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 5. Create a Docker Container for Jenkins
Run the following command in the directory where `docker-compose.yml` is located:

- Start Jenkins using Docker Compose:
  ```sh
  docker-compose up -d
  ```

  **docker-compose up** → Starts the **containers** defined in the `docker-compose.yml` file. If they don’t exist, it creates them.

  **-d** (detached mode) → **Runs the containers** in the **background**, so the **terminal is free** for other tasks. 

- Verify that the **container** is running:
  ```sh
  docker ps
  ```
- To see the logs
  ```sh
  docker logs -f jenkins
  ```
  **`docker logs`** → Displays the logs (records) of a running container.

  **`-f` (follow)** → Keeps updating the logs in real-time. It’s like watching live logs as the container generates new entries.

  **`jenkins`** → The **name of the container** whose logs you want to view.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 6. Access Jenkins
1. **Access Jenkins Web Interface:**
   - Open a web browser and go to [http://localhost:8080](http://localhost:8080).
   - This will load the Jenkins setup page.

2. **Unlock Jenkins:**
   - When prompted, enter the **initial admin password** that you obtained with the following command:
 
    **PowerShell or CMD**
    ```sh
    docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
    ```
    **Git Bash**
    ```sh
    docker exec jenkins cat //var/jenkins_home/secrets/initialAdminPassword
    ```
   - Paste the password into the "**Administrator password**" field on the web page.

3. **Customize Jenkins Installation:**
   - Once Jenkins is unlocked, you will be presented with two options:
     - **Install suggested plugins**: Recommended for most users. Jenkins will automatically install the most commonly used plugins.
     - **Select plugins to install**: If you want to customize your Jenkins installation by selecting specific plugins, choose this option.
   - **Choose one of these options** based on your needs.

4. **Create Admin User:**
   - After plugin installation, you will be asked to create an **admin user**.
   - Fill in the required fields:
     - **Username**: admin
     - **Password**: *****
     - **Full name**: Jenkins Admin
     - **E-mail address**: *****@gmail.com
   - After filling in the fields, click **Save and Continue**.

5. **Complete Setup:**
   - Jenkins will confirm that the setup is complete.
   - Click **Start using Jenkins** to access the Jenkins dashboard.

6. **Configure Jenkins:**
   - You can now start configuring your Jenkins installation by adding new jobs, pipelines, and setting up additional configurations.

**Additional Commands**

Stop Jenkins:
```sh
docker-compose down
```

Restart Jenkins:
```sh
docker-compose up -d
```

Interact with the container
```sh
docker exec -ti jenkins bash
```  
To view the Java version
```sh
java -version
 ```
To exit
```sh
exit
 ```
**`docker exec`**:
   - This command is used to run a command in a running container.
   - It allows you to interact with the container’s file system and environment.

**`-ti`**:
   - **`-t`**: This flag allocates a pseudo-TTY, which means it enables terminal features like command-line input and output.
   - **`-i`**: This flag stands for "interactive" and keeps the standard input open, which allows you to interact with the container in real-time.

**`jenkins`**:
   - This is the **name of the running container**. It is the name or ID of the container where the command will be executed. In this case, it refers to a container running Jenkins.

**`bash`**:
   - This is the command being executed inside the container. It launches the **Bash shell** inside the Jenkins container, allowing you to interact with the container as if you were logged into a Linux terminal.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

## Section 3: Getting Started with Jenkins

### 1. Create Your First Jenkins Job

To create your first Jenkins job, follow these steps:

1. **Access Jenkins Dashboard:**
   Open Jenkins in your browser by navigating to `http://localhost:8080` (or the URL where your Jenkins is running).

2. **Create a New Job:**
   - On the Jenkins Dashboard, click on **`+ New Item`**.
   - Enter a name for your job (**e.g**., `my-first-job`).
   - Select **Freestyle project** and click **`OK`**.

3. **Configure Your Job:**
   1. Click on **Build Steps** .
   2. Click on **Add build step** and select **Execute shell** (or **Execute Windows batch command** if you're using Windows). 
   3. In the **Command** field, enter the following script:

      ```bash
      echo Hello World
      ```
   - Click **`Save`** once you’re done.

4. **Run the Job:**
   - After saving the job, you can run it by clicking **Build Now** on the job's page.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

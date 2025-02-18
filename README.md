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
  - [2. Keep Playing with Your First Jenkins Job](#2-keep-playing-with-your-first-jenkins-job)
  - [3. Redirect your first Job's output](#3-redirect-your-first-jobs-output)
  - [4. Learn how to execute a bash script from Jenkins](#4-learn-how-to-execute-a-bash-script-from-jenkins)
  - [5. Add parameters to your Job](#5-add-parameters-to-your-job)
  - [6.Learn How to Create a Jenkins List Parameter with Your Script](#6learn-how-to-create-a-jenkins-list-parameter-with-your-script)


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

### 2. Keep Playing with Your First Jenkins Job

**Steps to Modify Your Jenkins Job**

**1. Open Your Existing Job**

1. Navigate to the **Jenkins Dashboard**.
2. Find and click on the job you created earlier, e.g., `my-first-job`.

**2. Modify the Build Step**

1. On the job configuration page, click on **Build Steps** section where you previously added the shell script.
2. Replace the current command with the following script:

   ```bash
   echo "Current date and time is $(date)"
   ```
3. Click on **`Save`**
4. Click on **`Build Now`***

**Console Output**

```
Started by user Jenkins Admin
Running as SYSTEM
Building in workspace /var/jenkins_home/workspace/my-first-job
[my-first-job] $ /bin/sh -xe /tmp/jenkins14591664813078710572.sh
+ date
+ echo Current date and time is Tue Feb 18 19:48:12 UTC 2025
Current date and time is Tue Feb 18 19:48:12 UTC 2025
Finished: SUCCESS
```
<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 3. Redirect your first Job's output
Replace the current command with the following script:

```bash
NAME=Ovidio
echo "Hello, $NAME. Current date and time is $(date)" > /tmp/info
```
**Output**
```bash
Started by user Jenkins Admin
Running as SYSTEM
Building in workspace /var/jenkins_home/workspace/my-first-job
[my-first-job] $ /bin/sh -xe /tmp/jenkins9811356184091446742.sh
+ NAME=Ovidio
+ date
+ echo Hello, Ovidio. Current date and time is Tue Feb 18 19:56:12 UTC 2025
Finished: SUCCESS
```

After running it you can use the following commands:

```bash
docker exec -ti jenkins bash
```

```bash
cat /tmp/info
```
**Output**
```bash
Hello, Ovidio. Current date and time is Tue Feb 18 19:56:12 UTC 2025
```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 4. Learn how to execute a bash script from Jenkins

**1. Create a Shell Script**

First, create a script outside of the Jenkins container, since containers typically have only essential packages.

1. Create a new script file named `script.sh`.
2. Edit the file using a text editor like `vi`:

   ```sh
   vi script.sh
   ```

4. Press `i` to enter insert mode and add the following content:

   ```sh
   #!/bin/bash
   echo "Hello, $1 $2"
   ```

5. Save and exit (`ESC` → `:wq` → `Enter`).

6. Give the script executable permissions:

   ```sh
   chmod +x script.sh
   ```
   **chmod** → Changes file permissions.  
   **+x** → Adds execution permissions (**allows the file to be run as a program**).

**2. Copy the Script to the Jenkins Container**

Since the script was created outside the container, copy it inside using `docker cp`:

```sh
docker cp script.sh jenkins:/tmp/script.sh
```
This command copies a file from the **`host machine`** to a **`Docker container`**.

**docker cp** → The Docker command to copy files between **`the host`** and **`a container`**.  
**script.sh** → The file on the host machine that you want to copy.  
**jenkins:/tmp/script.sh** → The destination inside the container:  
  - **jenkins** → The name or container ID of the running container.  
  - **/tmp/script.sh** → The target location inside the container where the file will be placed.  

**Output:**
```sh
Successfully copied 2.05kB to jenkins:/tmp/script.sh
```

**3. Verify the Script in the Container**

1. Access the Jenkins container:

   ```sh
   docker exec -ti jenkins bash
   ```

2. Check if the script is inside `/tmp/`:

   ```sh
   ls /tmp/script.sh
   ```

3. Execute the script manually:

   ```sh
   /tmp/script.sh John Doe
   ```

**Expected output:**

```sh
Hello, John Doe
```

**4. Configure a Jenkins Job to Run the Script**

1. Open **Jenkins Dashboard**.
2. Create a new **Freestyle Project**.
3. Go to **Build Steps** → **Add build step** → **Execute shell**.
4. Enter the command:

   ```sh
   /tmp/script.sh John Doe
   ```

5. Save the job.

**5. Run and Verify the Job**

1. Click **Build Now**.
2. Check the console output:

   ```sh
   Hello, John Doe
   ```

**6. Using Variables Instead of Hardcoded Values**

Modify the job to use Jenkins environment variables:

1. Edit the job's **Execute shell** command:

   ```sh
   NAME="John"
   LASTNAME="Doe"
   /tmp/script.sh "$NAME" "$LASTNAME"
   ```

2. Save and re-run the job.

**7. Debugging Errors**

- If the job fails, check the **Console Output**.
- Failed jobs appear in **red**, while successful ones are **blue**.
- Common issues:
  - Incorrect file path → Verify with `ls /tmp/`.
  - Missing execute permissions → Run `chmod +x /tmp/script.sh`.
  - Syntax errors in the script → Check using `bash -n script.sh`.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 5. Add parameters to your Job

**1. Open Job Configuration**
1. Navigate to **Jenkins Dashboard**.
2. Select the job you want to modify.
3. Click on **Configure**.

**2. Enable Parameters in the Job**
1. In the **General** section, check the box **This project is parameterized**.
2. Click **Add Parameter** and select **String Parameter**.

**3. Define the Parameters**
1. Add a **First Name** parameter:
   - Name: `FIRST_NAME`
   - Default Value: `Simon`
2. Add a **Second Name** parameter:
   - Name: `SECOND_NAME`
   - Default Value: `Ovidio`

![Define the Parameters](/images/add_parameters_to_your_job.png)

**4. Modify the Job to Use Parameters**
1. In the **Build** section, select **Execute shell**.
2. Replace any hardcoded names with the parameters:
   ```sh
   echo "Hello $FIRST_NAME $SECOND_NAME"
   ```
3. Click **Save**.

**5. Execute the Job with Parameters**
1. Click **`Build with Parameters`**.
2. Enter **`new values`** (or use default values).

![Define the Parameters](/images/add_parameters_to_your_job_2.png)

3. Click **Build**.

**6. Check the Output**
1. Click on the new build instance.
2. Select **Console Output**.
3. You should see the dynamic greeting:
   ```
   Hello Simon Ovidio
   ```

**Benefits of Using Parameters**
- **Dynamic Inputs**: Modify values without changing the job configuration.
- **Reusability**: Use **the same job** for `different scenarios`.
- **Environment Flexibility**: Pass variables like `dev`, `staging`, or `production` dynamically.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 6.Learn How to Create a Jenkins List Parameter with Your Script

**1. Open Job Configuration**

1. Navigate to your Jenkins instance.
2. Select the job you want to configure.
3. Click on **Configure**.

**2. Enable Parameterization**

1. In the **General** section, check the box **This project is parameterized**.
2. Click on **Add Parameter**.
3. Select **Choice Parameter**.

**3. Define the List Parameter**

1. In the **Name** field, enter a variable name (e.g., `LASTNAME`).
2. In the **Choices** field, define the possible values, one per line:
   ```
   Smith
   Johnson
   Doe
   ```
![List Parameter](images/list_parameter_0.png)

3. Click **Save**.

**4. Modify the Build Script to Use the Parameter**

In the **Build Steps** section:

1. Click **Add build step** → **Execute shell**.
2. Enter the following script:
   ```sh
   echo "Hello, $FIRST_NAME $SECOND_NAME $LASTNAME"
   ```
3. Click **Save**.

**5. Trigger a Build with Parameters**
1. Click on **Build with Parameters**.
2. Enter values for `FIRST_NAME` and `SECOND_NAME`.
3. Select a value from the `LASTNAME` dropdown list.
4. Click **`Build`**.
![Build Parameters](images/list_parameter.png)

**6. Verify the Output**
1. Click on the completed build.
2. Go to **Console Output**.
3. You should see an output similar to:
   ```sh
   Hello, Simon Ovidio Smith
   ```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

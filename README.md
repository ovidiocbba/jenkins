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
  - [7. Add basic logic and boolean parameters](#7-add-basic-logic-and-boolean-parameters)
- [Section 4: Jenkins \& Docker](#section-4-jenkins--docker)
  - [1. Docker + Jenkins + SSH](#1-docker--jenkins--ssh)
  - [2. Learn how to install Jenkins Plugins (SSH Plugin)](#2-learn-how-to-install-jenkins-plugins-ssh-plugin)
  - [3. Integrate your Docker SSH server with Jenkins](#3-integrate-your-docker-ssh-server-with-jenkins)
  - [4. Run your a Jenkins job on your Docker remote host through SSH](#4-run-your-a-jenkins-job-on-your-docker-remote-host-through-ssh)
- [Section 5: Jenkins \& AWS](#section-5-jenkins--aws)
  - [1. Create a MySQL server on Docker](#1-create-a-mysql-server-on-docker)
  - [2. Install MySQL Client and AWS CLI](#2-install-mysql-client-and-aws-cli)
  - [3. Create a MySQL Database](#3-create-a-mysql-database)
  - [4. Creating an S3 Bucket on AWS](#4-creating-an-s3-bucket-on-aws)
  - [5. Create a user (IAM) for AWS authentication](#5-create-a-user-iam-for-aws-authentication)
  - [6. Learn how to take a backup and upload it manually to S3](#6-learn-how-to-take-a-backup-and-upload-it-manually-to-s3)
  - [7. Automate the backup and upload process with a shell script](#7-automate-the-backup-and-upload-process-with-a-shell-script)
  - [8. Learn how to manage sensitive information in Jenkins (Keys, Passwords)](#8-learn-how-to-manage-sensitive-information-in-jenkins-keys-passwords)
- [Section 7: Jenkins \& Security](#section-7-jenkins--security)
  - [1. Intro - Learn how to Enable/Disable Login in Jenkins](#1-intro---learn-how-to-enabledisable-login-in-jenkins)
  - [2. Allow users to sign up](#2-allow-users-to-sign-up)
  - [3. Install a powerful security plugin](#3-install-a-powerful-security-plugin)
  - [4. Ever heard about roles? Let's create a Read Only role!](#4-ever-heard-about-roles-lets-create-a-read-only-role)
  - [5. Create a role to execute jobs, and assign that role to your user](#5-create-a-role-to-execute-jobs-and-assign-that-role-to-your-user)
  - [6. Learn how to restrict Jobs to users using Project Roles](#6-learn-how-to-restrict-jobs-to-users-using-project-roles)
- [Section 8: Jenkins Tips \& Tricks](#section-8-jenkins-tips--tricks)
  - [1. Global environment variables in Jenkins](#1-global-environment-variables-in-jenkins)
  - [2. Create your own custom global environment variables](#2-create-your-own-custom-global-environment-variables)
  - [3. Modify the Jenkins URL](#3-modify-the-jenkins-url)
  - [4. Meet the Jenkins' cron: Learn how to execute Jobs automatically](#4-meet-the-jenkins-cron-learn-how-to-execute-jobs-automatically)
  - [5. Troubleshooting: Githooks throwing 403 forbidden errors?](#5-troubleshooting-githooks-throwing-403-forbidden-errors)
  - [6.Trigger your Jobs from Bash Scripts (No parameters)](#6trigger-your-jobs-from-bash-scripts-no-parameters)
  - [7.Trigger your Jobs from Bash Scripts (With Parameters)](#7trigger-your-jobs-from-bash-scripts-with-parameters)
- [Section 9: Jenkins \& Email](#section-9-jenkins--email)
  - [1.Install a Mail Plugin](#1install-a-mail-plugin)
  - [2. Integrate Jenkins and AWS Simple Email Service](#2-integrate-jenkins-and-aws-simple-email-service)
  - [3. Integrate Jenkins and Gmail](#3-integrate-jenkins-and-gmail)
  - [4. Integrating Email Notifications into Jenkins Jobs](#4-integrating-email-notifications-into-jenkins-jobs)
- [Section 10: Jenkins \& Maven](#section-10-jenkins--maven)
  - [1. Install the Maven Plugin](#1-install-the-maven-plugin)
  - [2. Install the GIT Plugin](#2-install-the-git-plugin)
  - [3. Learn how to clone a GIT/GITHUB repository from Jenkins](#3-learn-how-to-clone-a-gitgithub-repository-from-jenkins)
  - [4. Learn how to build a JAR using maven](#4-learn-how-to-build-a-jar-using-maven)
  - [5. Learn how to test your code](#5-learn-how-to-test-your-code)
  - [6. Deploying Your JAR Locally](#6-deploying-your-jar-locally)
  - [7. Display the result of your tests using a graph](#7-display-the-result-of-your-tests-using-a-graph)
  - [8. Archive the last successful artifact](#8-archive-the-last-successful-artifact)
  - [9. Send Email notifications about the status of your maven project](#9-send-email-notifications-about-the-status-of-your-maven-project)
- [Section 11: Jenkins \& GIT](#section-11-jenkins--git)
  - [1. Create a Git Server using Docker](#1-create-a-git-server-using-docker)
  - [2. Create your first Git Repository](#2-create-your-first-git-repository)
  - [3. Create a Git User to Interact with Your Repository](#3-create-a-git-user-to-interact-with-your-repository)
  - [4. Upload the code for the Java App in your Repo](#4-upload-the-code-for-the-java-app-in-your-repo)
  - [5. Learn about Git Hooks](#5-learn-about-git-hooks)
  - [6. Trigger your Jenkins job using a Git Hook](#6-trigger-your-jenkins-job-using-a-git-hook)
- [Section 12: Jenkins \& DSL](#section-12-jenkins--dsl)
  - [1. Install the DSL Plugin](#1-install-the-dsl-plugin)
  - [2. What is a Seed Job in DSL?](#2-what-is-a-seed-job-in-dsl)
  - [3. Understand the DSL Structure](#3-understand-the-dsl-structure)
  - [4. Adding a Description to a Job in DSL](#4-adding-a-description-to-a-job-in-dsl)
  - [5. Parameters](#5-parameters)
- [Section 13: CI/CD - Definitions](#section-13-cicd---definitions)
  - [1. Introduction to CI/CD](#1-introduction-to-cicd)
  - [2. Continuous Integration](#2-continuous-integration)
  - [3. Continuous Delivery](#3-continuous-delivery)
  - [4. Continuous Deployment](#4-continuous-deployment)
- [Section 14: Jenkins Pipeline - Jenkinsfile](#section-14-jenkins-pipeline---jenkinsfile)
  - [1. Introduction to Pipeline](#1-introduction-to-pipeline)
  - [2. Introduction to Jenkinsfile](#2-introduction-to-jenkinsfile)
  - [3. Install the Jenkins Pipeline Plugin](#3-install-the-jenkins-pipeline-plugin)
  - [4. Create your first Pipeline](#4-create-your-first-pipeline)
  - [5. Add multi-steps to your Pipeline](#5-add-multi-steps-to-your-pipeline)
  - [6. Retry](#6-retry)
  - [7. Timeouts](#7-timeouts)
  - [8. Environment variables](#8-environment-variables)
  - [9. Credentials](#9-credentials)
  - [10. Post actions](#10-post-actions)
- [Section 15: CI/CD + Jenkins Pipeline + Docker +  Maven](#section-15-cicd--jenkins-pipeline--docker---maven)
  - [1. Introduction](#1-introduction)
  - [2. Notes on Docker in Docker](#2-notes-on-docker-in-docker)
  - [3. Learn how to install Docker inside of a Docker Container](#3-learn-how-to-install-docker-inside-of-a-docker-container)
  - [4. Define the steps for your Pipeline](#4-define-the-steps-for-your-pipeline)
  - [5. Notes on building a jar with docker](#5-notes-on-building-a-jar-with-docker)
  - [8. Notes on creating the Dockerfile](#8-notes-on-creating-the-dockerfile)
  - [9. Build: Create a Dockerfile and build an image with your Jar](#9-build-create-a-dockerfile-and-build-an-image-with-your-jar)
- [Result](#result)
  - [10. Build: Create a Docker Compose file to automate the Image build process](#10-build-create-a-docker-compose-file-to-automate-the-image-build-process)
  - [11. Build: Write a bash script to automate the Docker Image creation process](#11-build-write-a-bash-script-to-automate-the-docker-image-creation-process)
  - [12. Build: Add your scripts to the Jenkinsfile](#12-build-add-your-scripts-to-the-jenkinsfile)
  - [13. Test: Learn how to test your code using Maven and Docker](#13-test-learn-how-to-test-your-code-using-maven-and-docker)
  - [14. Test: Create a bash script to automate the test process](#14-test-create-a-bash-script-to-automate-the-test-process)
  - [15. Test: Add your test script to Jenkinsfile](#15-test-add-your-test-script-to-jenkinsfile)
  - [16. Create a remote machine to deploy your containerized app](#16-create-a-remote-machine-to-deploy-your-containerized-app)
  - [17. Push: Create your own Docker Hub account](#17-push-create-your-own-docker-hub-account)
  - [18. Push: Create a Repository in Docker Hub](#18-push-create-a-repository-in-docker-hub)
  - [19. Push: Learn how to Push/Pull Docker images to your Repository](#19-push-learn-how-to-pushpull-docker-images-to-your-repository)
  - [20. Push: Write a bash script to automate the push process](#20-push-write-a-bash-script-to-automate-the-push-process)
  - [21. Push: Add your push script to Jenkinsfile](#21-push-add-your-push-script-to-jenkinsfile)
  - [22. Deploy: Transfer some variables to the remote machine](#22-deploy-transfer-some-variables-to-the-remote-machine)
  - [23. Deploy: Deploy your application on the remote machine manually](#23-deploy-deploy-your-application-on-the-remote-machine-manually)
  - [24. Deploy: Transfer the deployment script to the remote machine](#24-deploy-transfer-the-deployment-script-to-the-remote-machine)
  - [25. Deploy: Execute the deploy script in the remote machine](#25-deploy-execute-the-deploy-script-in-the-remote-machine)
  - [26. Deploy: Add your deploy script to Jenkinsfile](#26-deploy-add-your-deploy-script-to-jenkinsfile)
  - [27. Create a Git Repository to store your scripts and the code for the app](#27-create-a-git-repository-to-store-your-scripts-and-the-code-for-the-app)
  - [28. Create the Jenkins Pipeline. Finally!](#28-create-the-jenkins-pipeline-finally)
  - [29. Modify the path when mounting Docker volumes](#29-modify-the-path-when-mounting-docker-volumes)
  - [30. Create the Registry Password in Jenkins](#30-create-the-registry-password-in-jenkins)
  - [31. Add the private ssh key to the Jenkins container](#31-add-the-private-ssh-key-to-the-jenkins-container)
  - [32. Add post actions to Jenkinsfile](#32-add-post-actions-to-jenkinsfile)
  - [33. Execute your Pipeline manually](#33-execute-your-pipeline-manually)
  - [34. Notes on Git Hooks](#34-notes-on-git-hooks)
  - [35. Create a Git Hook to automatically trigger your Pipeline](#35-create-a-git-hook-to-automatically-trigger-your-pipeline)
  - [36. Start the CI/CD process by committing new code to Git!](#36-start-the-cicd-process-by-committing-new-code-to-git)

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

### 7. Add basic logic and boolean parameters

**1. Modify the Script to Include a Boolean Parameter**

First, we add a script to include a new parameter called `SHOW`, which is a boolean value (true/false). This parameter determines whether the script prints the user's name and last name.

1. Edit your script to include a new boolean parameter `SHOW`.
2. Implement a conditional statement:
   - If `SHOW` is true, print the user's first and last name.
   - Otherwise, display an error message.

```bash
#!/bin/bash
NAME = $1
LASTNAME = $2
SHOW = $3
if [ "$SHOW" = "true" ]; then
    echo "Hello, $NAME $LASTNAME"
else
    echo "If you want to see the name, please mark the show option."
fi
```
**2. Copy the Script to the Jenkins Container**
Since we made modifications to our script, we need to copy it back to the Jenkins container:

```bash
docker cp script2.sh jenkins:/tmp/script2.sh
```

Then, enter the container and verify the script:

```bash
docker exec -it jenkins bash
```

```bash
cat /tmp/script2.sh
```
**Test 1**
```bash
/tmp/script2.sh Ovidio Miranda false
```
**Output**
```bash
If you want to see the name, please mark the show option.
```
**Test 2**
```bash
/tmp/script2.sh Ovidio Miranda true
```
**Output**
```bash
Hello, Ovidio Miranda 
```

**3. Configure the Jenkins Job**

1. Navigate to the Jenkins job configuration page.
2. Click on `This project is parameterized`.
3. Add a new boolean parameter:
   - **Name**: `SHOW`
   - **Default Value**: `true` (checked) or `false` (unchecked)

![Boolean Parameters](images/boolean_parameters_1.png)

In the **Build Steps** section:

4. Enter the following script:
   ```sh
   /tmp/script2.sh $FIRST_NAME $LASTNAME $SHOW
   ```
5. Click **Save**.


**4. Execute the Jenkins Job**

1. Click on `Build with Parameters`.
2. Enter values for:
   - **First Name** (string parameter)
   - **Last Name** (choice parameter from a list)
   - **SHOW** (boolean parameter: checked = true, unchecked = false)

![Boolean Parameters](images/boolean_parameters_2.png)

3. Click `Build`.
4. Check the console output to see if the correct logic was applied:
   - If `SHOW` is `true`, it should print `Hello, First Name Last Name`.
   - If `SHOW` is `false`, it should display an error message.

**5. Verify the Results**
- Run the job twice: once with `SHOW` set to `true` and once with `false`.
- Observe how the output changes based on the parameter value.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

## Section 4: Jenkins & Docker
**Setting Up SSH for Remote Server Access**

**Step 1: Generate SSH Key Pair**

To create a secure SSH key pair, use the following command:

```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com" -f ~/.ssh/id_rsa_remote
```

**Explanation:**

- `-t rsa` → Specifies the **RSA algorithm** for key generation.
- `-b 4096` → Generates a **`4096-bit key`** for stronger encryption.
- `-C "your_email@example.com"` → Adds an optional **comment** (e.g., your email) for identification.
- `-f ~/.ssh/id_rsa_remote` → **Saves the key pair** with the `specified name`.

After running this command:
- You will have two files: `id_rsa_remote` **(private key)** and `id_rsa_remote.pub` **(public key)**.
- The private key remains on your local machine, while the **`public key`** must be **added to the remote server**.

**Step 2: Configure SSH Client**

Create or **edit** the SSH configuration file **on your local machine**:

```sh
nano ~/.ssh/config
```

Add the following configuration:

```sh
Host myremote
    HostName remote_host
    User remote_user
    IdentityFile ~/.ssh/id_rsa_remote
    Port 22
```

**Explanation:**

- `Host myremote` → Defines a shortcut name for the remote server.
- `HostName your.server.ip` → Specifies the server’s IP address or **domain**.
- `User your_remote_user` → Defines the username to use for connection.
- `IdentityFile ~/.ssh/id_rsa_remote` → Specifies the private key to use.
- `Port 22` → Defines the SSH port (default is 22).

### 1. Docker + Jenkins + SSH

**Copy the Public Key to the Build Context**

Move **the generated public key** to the **`centos7`** directory, where the `Dockerfile is located`:

```shell
cp ~/.ssh/id_rsa_remote.pub .
```

**Create a Docker image using a docker file**

Before building the **Docker image**, ensure that `id_rsa_remote.pub` is copied into **the same directory** as the **Dockerfile**:

**Dockerfile**
```dockerfile
# Use CentOS 7 as the base image
FROM centos:7

# Reconfigure the repository to use CentOS Vault
RUN sed -i 's|mirrorlist=http://mirrorlist.centos.org|#mirrorlist=http://mirrorlist.centos.org|g' /etc/yum.repos.d/CentOS-Base.repo && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-Base.repo

# Install the OpenSSH server
RUN yum -y install openssh-server

# Line 1: Add a new user 'remote_user'  
# Line 2: Set up the user's password (WARNING: Change this in production)  
# Line 3: Create the SSH directory for the user  
# Line 4: Set proper permissions to secure the SSH directory
RUN useradd remote_user && \
    echo "1234" | passwd remote_user --stdin && \  
    mkdir /home/remote_user/.ssh && \ 
    chmod 700 /home/remote_user/.ssh  

# Copy the public key to the authorized_keys file for passwordless SSH access
COPY id_rsa_remote.pub /home/remote_user/.ssh/authorized_keys

# Change ownership of the home directory and set correct permissions for the key
# Line 1: Give ownership to the user
RUN chown remote_user:remote_user -R /home/remote_user && \  
    chmod 400 /home/remote_user/.ssh/authorized_keys  # Secure the authorized_keys file

# Generate necessary SSH host keys
RUN ssh-keygen -A

# Start the SSH service and keep the container running
# The "-D" flag prevents sshd from running as a background daemon,
# ensuring the container does not exit immediately after startup.
CMD /usr/sbin/sshd -D
```
**Create a docker-compose.yml**

The `docker-compose.yml` defines the services needed to connect **Jenkins to the remote server** (remote_host).

`jenkins`: Runs **Jenkins**, which can `connect` to **remote_host** `via SSH`  
`remote_host`: Runs the SSH server inside a container.

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
  remote_host:
    container_name: remote-host
    image: remote-host
    build:
      context: . # Define the build context ('Dockerfile' should be inside the 'centos7' directory)
    networks:
      - net

networks:
  net: # Define a custom Docker network to enable communication between containers

volumes:
  jenkins_home_data: # Define a persistent volume for Jenkins data storage
```
Run the following code to create the image:

```shell
docker-compose build
```
![Docker](images/docker_jenkins_ssh_1.png)

 
To see that the image was created successfully(`remote-host`)
```shell
docker images
```
![Docker](images/docker_jenkins_ssh_2.png)

Start the services (`jenkins` and `remote_host`)
```shell
docker-compose up -d
```
![Docker](images/docker_jenkins_ssh_3.png)

**Accessing the Remote Host from Jenkins**

```bash
docker exec -it jenkins bash
```

```bash
yes
```
```bash
yes
```
Enter the password that was previously set.
```bash
1234
```
![Docker](images/docker_jenkins_ssh_4.png)

**Connect from Jenkins to remote_host using SSH:**

```bash
docker exec -it jenkins bash
```
```bash
ssh remote_user@remote_host
```
Enter the password that was previously set.
```bash
1234
```

**Output**
```shell
$ docker exec -it jenkins bash
jenkins@561dd820647f:/$ ssh remote_user@remote_host
remote_user@remote_host's password:
Last login: Thu Feb 20 00:37:28 2025 from jenkins.centos7_net
[remote_user@2719f66fe039 ~]$
```

To check the connection:

```bash
ping remote_host
```
**Output**
```shell
[remote_user@2719f66fe039 ~]$ ping remote_host
PING remote_host (172.20.0.2) 56(84) bytes of data.
64 bytes from 2719f66fe039 (172.20.0.2): icmp_seq=1 ttl=64 time=1.61 ms
64 bytes from 2719f66fe039 (172.20.0.2): icmp_seq=2 ttl=64 time=0.029 ms
64 bytes from 2719f66fe039 (172.20.0.2): icmp_seq=3 ttl=64 time=0.037 ms
64 bytes from 2719f66fe039 (172.20.0.2): icmp_seq=4 ttl=64 time=0.035 ms
```

**Using Private Key Instead of Password**

If you don't want to enter the password you can add your private key:

Move the generated **`private key`** to the **centos7** directory, where the **Dockerfile** is located:
```shell
cp ~/.ssh/id_rsa_remote .
```
Move the **private key** to the `jenkins` container:
```shell
docker cp id_rsa_remote jenkins:/tmp/id_rsa_remote
```
**Output**
```shell
$ docker cp id_rsa_remote jenkins:/tmp/id_rsa_remote
Successfully copied 5.12kB to jenkins:/tmp/id_rsa_remote
```
To see your private key
```bash
docker exec -it jenkins bash
cd /tmp/
ls
```
**Output**
```bash
$ docker exec -it jenkins bash
jenkins@561dd820647f:/$ cd /tmp/
jenkins@561dd820647f:/tmp$ ls
hsperfdata_jenkins  jetty-0_0_0_0-8080-war-_-any-7277700481180075564
id_rsa_remote       winstone10295603392971035092.jar
jenkins@561dd820647f:/tmp$
```

**To log in without a password:**

Log in using your `private key` file:(You no longer need to enter the key)
```bash
ssh -i id_rsa_remote remote_user@remote_host
```
**Output**
```shell
jenkins@561dd820647f:/tmp$ ssh -i id_rsa_remote remote_user@remote_host
Last login: Thu Feb 20 00:37:44 2025 from jenkins.centos7_net
[remote_user@2719f66fe039 ~]$
```
This setup allows secure SSH access between Jenkins and a remote server.

**To enter the remote host**
```shell
docker exec -it remote-host bash
cat /etc/centos-release
```
**Output**
```bash
$ docker exec -it remote-host bash
[root@2719f66fe039 /]# cat /etc/centos-release
CentOS Linux release 7.9.2009 (Core)
```
**Check if the package is installed**

**OpenSSH server**

```shell
rpm -q openssh-server
```

**Output**

```shell
[root@2719f66fe039 /]# rpm -q openssh-server
openssh-server-7.4p1-23.el7_9.x86_64
```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 2. Learn how to install Jenkins Plugins (SSH Plugin)

1. Navigate to **Manage Jenkins** > **Plugins**.
2. Click on **Available Plugins**.
3. Search for the plugin by typing `SSH` in the search bar.
4. Select the **SSH** plugin from the search results.
5. Click the **Install** button.
6. Wait for the installation to complete and restart Jenkins if necessary.

![SSH Plugin](images/ssh_plugin_1.png)

**Note:**

Due to these warnings the test was not performed.

### 3. Integrate your Docker SSH server with Jenkins

**Step 1: Add SSH Credentials**

1. Select **Jenkins** > **Global credentials**.
2. Click **Add Credentials**.
3. For **Kind**, select **SSH Username with private key**.
4. Enter the following:
   - **Username:** `remote_user` (the user created in your Dockerfile).
   - **Private Key:** Copy the content of your private key file (e.g., `remote-key`) using:
     
    ```bash
    cat centos7/remote-key
    ```
5. Paste the private key into the Jenkins form.
6. Click **OK**.

![SHH credentials](images/docker_SSH_server_with_jenkins_1.png)

**Step 2: Add SSH Remote Host in Jenkins**

1. Go to the **Jenkins dashboard**.
2. Navigate to **Manage Jenkins** > **System Configuration** > **System**
3. Scroll down to **SSH remote hosts**.
4. Click **Add**.
5. Enter the following:
   - **Hostname:** `remote_host` (as defined in the Docker Compose file).
   - **Port:** `22` (default SSH port).
6. Select the **Credentials** from the dropdown (the `remote_user` credentials created earlier).
7. Click **Check the connection**.
8. Click **Save** to finalize the configuration.
9. Jenkins is now configured to communicate with the remote host via SSH.

✅ If successful, you will see a confirmation message.

![SHH credentials](images/docker_SSH_server_with_jenkins_2.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 4. Run your a Jenkins job on your Docker remote host through SSH

**1. Create a New Jenkins Job**

1. Open Jenkins and navigate to the main dashboard.
2. Click on **New Item**.
3. Enter a name for your job (e.g., `remote-task`).
4. Select **Freestyle Project**.
5. Click **OK**.

You should now see the configuration screen for the new job.

**2. Configure the Build Section**

1. Scroll down to the **Build Steps** section.
2. Click **Add build step**.
3. Select **Execute shell script on remote host using SSH**.
4. In the dropdown, **select the remote host** you have configured.
   - If you only have one SSH configuration, it will appear here.
5. **`SSH site:`** remote_user@remote_host:22
6. Enter the command you want to run on the remote host.

**Example:**

```bash
NAME=Ricardo

# Redirect output to a file
echo "Hello, $NAME. Current date and time is: $(date)" > /tmp/remote_file
```
![SHH Configuration](images/docker_SSH_server_with_jenkins_3.png)

This command creates a file called `remote_file` in the `/tmp` directory on the remote host.

**4. Run the Jenkins Job**

1. Save the configuration.
2. Click **Build Now**.
3. Open the **Console Output** to check the build logs.
4. The logs should indicate that the SSH script started and completed successfully.

![SHH Configuration](images/docker_SSH_server_with_jenkins_3_2.png)

---

**Verifying the Output**

1. Access your Jenkins container’s terminal:

`container_name`: remote-host

```bash
docker exec -it <container_name> bash
```

2. Check if the file exists in the Jenkins container:

```bash
ls /tmp/remote_file
```
![SHH Configuration](images/docker_SSH_server_with_jenkins_4.png)
✅ You should see the file on the `remote host`.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

## Section 5: Jenkins & AWS

### 1. Create a MySQL server on Docker

Create a `docker-compose.yml` file with the following content:

```yaml
services:
  jenkins:
    container_name: jenkins
    image: jenkins/jenkins:lts
    ports:
      - "8080:8080"
    volumes:
      - jenkins_home_data:/var/jenkins_home # Persist Jenkins data (configs, plugins, jobs)
    networks:
      - net # Define a custom Docker network
  remote_host:
    container_name: remote-host
    image: remote-host
    build:
      context: . # Define the build context ('Dockerfile' should be inside the 'centos7' directory)
    networks:
      - net
  db_host:
    container_name: db
    image: mysql:5.7
    environment:
      # Set the root password for MySQL
      MYSQL_ROOT_PASSWORD: "1234"  
    volumes:
      - db_data:/var/lib/mysql
    networks:
      - net

networks:
  net: # Define a custom Docker network to enable communication between containers

# These volumes (jenkins_home_data and db_data) 
# are managed by Docker and stored in its volume system
volumes:
  jenkins_home_data: 
  db_data:
```

To start the MySQL server with Docker Compose, run:

```bash
docker-compose up -d
```
**Output**
```bash
$ docker-compose up -d
[+] Running 3/3
 ✔ Container remote-host  Started                                                        1.1s
 ✔ Container jenkins      Started                                                        0.8s
 ✔ Container db           Started                                                        0.8s
```
![Jenkins AWS](images/jenkins_aws_1.png)

**Access the MySQL Server**

**Output**
```bash
docker exec -ti db bash
```
```bash
mysql -u root -p
```
Enter the password when prompted:

```bash
Enter password: 1234
```
**Outuput**
```bash
$ docker exec -ti db bash
bash-4.2# mysql -u root -p
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2
Server version: 5.7.44 MySQL Community Server (GPL)

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
```
**List Databases in MySQL**

To check the available databases, run:

```bash
show databases
```
**Output**
```bash
mysql> ;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.01 sec)

mysql>
```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 2. Install MySQL Client and AWS CLI

Before building the **Docker image**, ensure that `id_rsa_remote.pub` is copied into **the same directory** as the **Dockerfile**(`jenkins_aws`):

```dockerfile
# Use CentOS 7 as the base image
FROM centos:7

# Reconfigure the repository to use CentOS Vault
RUN sed -i 's|mirrorlist=http://mirrorlist.centos.org|#mirrorlist=http://mirrorlist.centos.org|g' /etc/yum.repos.d/CentOS-Base.repo && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-Base.repo

# Install the OpenSSH server
RUN yum -y install openssh-server

# Line 1: Add a new user 'remote_user'  
# Line 2: Set up the user's password (WARNING: Change this in production)  
# Line 3: Create the SSH directory for the user  
# Line 4: Set proper permissions to secure the SSH directory
RUN useradd remote_user && \
    echo "1234" | passwd remote_user --stdin && \  
    mkdir /home/remote_user/.ssh && \ 
    chmod 700 /home/remote_user/.ssh  

# Copy the public key to the authorized_keys file for passwordless SSH access
COPY id_rsa_remote.pub /home/remote_user/.ssh/authorized_keys

# Change ownership of the home directory and set correct permissions for the key
# Line 1: Give ownership to the user
RUN chown remote_user:remote_user -R /home/remote_user && \  
    chmod 400 /home/remote_user/.ssh/authorized_keys  # Secure the authorized_keys file

# Generate necessary SSH host keys
RUN ssh-keygen -A

# Install MySQL server
RUN yum -y install mysql

# Line 1: Install EPEL repository to enable additional packages 
# Line 2: Install Python 3 package manager (pip)
# Line 3: Upgrade pip to the latest version
# Line 4: Install AWS CLI for interacting with AWS services  
RUN yum -y install epel-release && \
    yum -y install python3-pip && \
    pip3 install --upgrade pip && \
    pip3 install awscli

# Start the SSH service and keep the container running
# The "-D" flag prevents sshd from running as a background daemon,
# ensuring the container does not exit immediately after startup.
CMD /usr/sbin/sshd -D
```
**Build the Docker Image**

Run the following command to **`build the Docker image`** and **see detailed logs**:

```shell
docker compose build --progress=plain
```
**Output**
```shell
--progress is a global compose flag, better use `docker compose --progress xx build ...
#0 building with "desktop-linux" instance using docker driver

#1 [remote_host internal] load build definition from Dockerfile
#1 transferring dockerfile: 1.92kB 0.0s done
#1 DONE 0.0s

#2 [remote_host internal] load metadata for docker.io/library/centos:7
#2 DONE 0.6s

#3 [remote_host internal] load .dockerignore
#3 transferring context: 2B done
#3 DONE 0.0s

#4 [remote_host 1/9] FROM docker.io/library/centos:7@sha256:be65f488b7764ad3638f236b7b515b3678369a5124c47b8d32916d6487418ea4
#4 resolve docker.io/library/centos:7@sha256:be65f488b7764ad3638f236b7b515b3678369a5124c47b8d32916d6487418ea4 0.0s done
#4 DONE 0.1s

#5 [remote_host internal] load build context
#5 transferring context: 794B 0.0s done
#5 DONE 0.0s

#6 [remote_host 2/9] RUN sed -i 's|mirrorlist=http://mirrorlist.centos.org|#mirrorlist=http://mirrorlist.centos.org|g' /etc/yum.repos.d/CentOS-Base.repo &&     sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-Base.repo
#6 CACHED

#7 [remote_host 3/9] RUN yum -y install openssh-server
#7 CACHED

#8 [remote_host 4/9] RUN useradd remote_user &&     echo "1234" | passwd remote_user --stdin &&     mkdir /home/remote_user/.ssh &&     chmod 700 /home/remote_user/.ssh
#8 CACHED

#9 [remote_host 5/9] COPY id_rsa_remote.pub /home/remote_user/.ssh/authorized_keys
#9 CACHED

#10 [remote_host 6/9] RUN chown remote_user:remote_user -R /home/remote_user &&     chmod 400 /home/remote_user/.ssh/authorized_keys  # Secure the authorized_keys file
#10 CACHED

#11 [remote_host 7/9] RUN ssh-keygen -A
#11 CACHED

#12 [remote_host 8/9] RUN yum -y install mysql
#12 0.696 Loaded plugins: fastestmirror, ovl
#12 0.909 Loading mirror speeds from cached hostfile
#12 3.043 Resolving Dependencies
#12 3.044 --> Running transaction check
#12 3.044 ---> Package mariadb.x86_64 1:5.5.68-1.el7 will be installed
#12 3.054 --> Processing Dependency: mariadb-libs(x86-64) = 1:5.5.68-1.el7 for package: 1:mariadb-5.5.68-1.el7.x86_64
```

**Recreate `remote-host` to Apply Changes**

After building the **Docker image**, restart the remote-host container to apply the new changes (**`MySQL and AWS CLI installation`**): 

```shell
docker-compose up -d
```

**Output**

```bash
$ docker-compose up -d
[+] Running 3/3
 ✔ Container jenkins      Running                                                          0.0s
 ✔ Container db           Running                                                          0.0s
 ✔ Container remote-host  Started                                                          0.9s
```
**Verify MySQL and AWS CLI Installation**

To access the **remote-host** container and verify that **MySQL and AWS CLI are installed**, use the following commands:

```bash
docker exec -ti remote-host bash
```
```bash
mysql --version
```
```bash
aws --version
```

**Output**
```bash
$ docker exec -ti remote-host bash
[root@9044da6c19a4 /]# mysql --version
mysql  Ver 15.1 Distrib 5.5.68-MariaDB, for Linux (x86_64) using readline 5.1
[root@9044da6c19a4 /]# aws --version
aws-cli/1.24.10 Python/3.6.8 Linux/5.15.167.4-microsoft-standard-WSL2 botocore/1.26.10
```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 3. Create a MySQL Database

**3.1 Access the Remote Host Container**

**To interact** with the MySQL database, first, access the **`remote host`** container:
```bash
docker exec -ti remote-host bash
```
**3.2 Connect to MySQL Server**

Use the following command to connect to MySQL. Replace `db_host` with the actual hostname or **container name running MySQL**:
```bash
mysql -u root -p -h db_host -p
```
When prompted, enter the password:

```bash
Enter password: 1234
```

**Output**

```bash
$ docker exec -ti remote-host bash
[root@9044da6c19a4 /]# mysql -u root -p -h db_host -p
Enter password:
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MySQL connection id is 2
Server version: 5.7.44 MySQL Community Server (GPL)

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MySQL [(none)]>
```

**3.3 Show Available Databases**

To list all databases:

```bash
show databases;
```

**Output**
```bash
MySQL [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
4 rows in set (0.02 sec)
```

**3.4 Create a New Database**

To create a new database named `testdb`:

```bash
create database testdb;
```
**Output**
```bash
MySQL [(none)]> create database testdb;
Query OK, 1 row affected (0.01 sec)
```
**3.5 Select the Database**

Use the newly created database:

```bash
use testdb;
```
**Output**
```bash
MySQL [(none)]> use testdb;
Database changed
```
**3.6 Create a Table**

Create a table named `info` with the following columns:

- **name**: VARCHAR(20)

- **lastname**: VARCHAR(20)

- **age**: INT(2)

```bash
create table info (name varchar(20), lastname varchar(20), age int(2));
```
**Output**
```bash
MySQL [testdb]> create table info (name varchar(20), lastname varchar(20), age int(2));
Query OK, 0 rows affected (0.05 sec)
```
**3.7 Describe Table Structure**

To check the structure of the info table:

```bash
describe info;
```
**Output**
```bash
MySQL [testdb]> describe info;
+----------+-------------+------+-----+---------+-------+
| Field    | Type        | Null | Key | Default | Extra |
+----------+-------------+------+-----+---------+-------+
| name     | varchar(20) | YES  |     | NULL    |       |
| lastname | varchar(20) | YES  |     | NULL    |       |
| age      | int(2)      | YES  |     | NULL    |       |
+----------+-------------+------+-----+---------+-------+
3 rows in set (0.01 sec)
```
**3.8 Insert Data into the Table**

To insert a new row into the info table:

```bash
insert into info values('ricardo', 'gonzales', 21);
```
**Output**
```bash
MySQL [testdb]> insert into info values('ricardo', 'gonzales', 21);
Query OK, 1 row affected (0.02 sec)
```

**3.9 Retrieve Data from the Table**

To retrieve all rows from the info table:

```bash
select * from info;
```
**Output**
```bash
MySQL [testdb]> select * from info;
+---------+----------+------+
| name    | lastname | age  |
+---------+----------+------+
| ricardo | gonzales |   21 |
+---------+----------+------+
1 row in set (0.01 sec)
```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 4. Creating an S3 Bucket on AWS

**What is Amazon S3?**

Amazon Simple **Storage Service** (Amazon S3) is an **object storage service** that provides scalable, high-speed, web-based cloud storage. It is commonly used for:
- Storing and **backing up data**.
- **Hosting static** websites.
- **Storing log files**, analytics, and big data processing.
- Serving media content (**images, videos**, etc.).
- Disaster recovery and data archiving.

**Prerequisites**
- An AWS account (If you do not have one, sign up at [AWS Console](https://aws.amazon.com/console/)).
- A valid credit card is required for account registration, but no charges will be applied unless resources are actively used.

**Steps to Create an S3 Bucket**

**1. Sign in to AWS Console**
1. Open your browser and search for "**AWS Console**" on Google.
2. Click on the official `AWS Console` link.
3. Click on **Sign in** and enter your AWS credentials.

**2. Navigate to the S3 Service**
1. Once signed in, click on the **Services** tab in the top navigation bar.
2. In the search bar, type "`S3`" and select the **S3** service.

**3. Create a New S3 Bucket**
1. Click on the **Create bucket** button.
  
![Image](images/creating_an_s3_bucket_1.png)

2. Enter a unique bucket name (e.g., `jenkins-mysql-backup`).
3. Click on the **Create** button to finalize the bucket creation.

![Image](images/creating_an_s3_bucket_2.png)
![Image](images/creating_an_s3_bucket_3.png)

**4. Uploading Files to S3 (Manually - Optional)**
1. Click on your newly created bucket.
2. Click on the **Upload** button.
3. Select the files you want to upload.
4. Click **Upload** to store them in the cloud.

![Image](images/creating_an_s3_bucket_4.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 5. Create a user (IAM) for AWS authentication

**What is IAM?**

AWS Identity and Access Management (IAM) is a service that helps you securely control access to AWS resources. It allows you to create and manage users, assign permissions, and enforce security policies.

**Why Create an IAM User?**

To upload backups to AWS, we need to authenticate using IAM credentials. Creating a dedicated IAM user ensures security and controlled access to AWS services like S3.

**Steps to Create an IAM User**

**1. Navigate to IAM Service**

1. Sign in to the AWS Management Console.
2. Click on the **Services** tab.
3. Search for **IAM** (Identity and Access Management) and select it.

**2. Add a New User**

1. In the IAM dashboard, go to the **Users** section on the left panel.
2. Click on the **Add user** button.
3. Enter a **User name** (e.g., `my-iam-user`).
4. Select **Programmatic access** to allow access via API, CLI, and SDK.
5. Click **Next: Permissions**.

![Image](images/create_a_user_iam.png)

**3. Assign Permissions**

1. Select **Attach existing policies directly**.
2. Search for `S3`.
3. For testing purposes, select **AmazonS3FullAccess** (Note: In real environments, restrict access to only required resources).
4. Click **Next: Tags** then Click **Next: Review** 

![Image](images/create_a_user_iam_0.png)

5. Click **Create User**.
![Image](images/create_a_user_iam_1.png)

**4. Retrieve Access Credentials**

1. After user creation, you will see an **Access Key ID** and **Secret Access Key**.
2. Click **Download .csv** to save these credentials securely.

![Image](images/create_a_user_iam_2.png)   

![Image](images/create_a_user_iam_3.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 6. Learn how to take a backup and upload it manually to S3

This guide explains how to manually create a MySQL backup and upload it to AWS S3 using the credentials created in a previous step. The process involves:
- Creating a MySQL backup using `mysqldump`
- Configuring AWS CLI authentication
- Uploading the backup to an S3 bucket

**Prerequisites**
- A running MySQL container
- AWS IAM credentials (Access Key ID and Secret Key)
- AWS CLI installed
- An existing S3 bucket

**1. Taking a MySQL Backup Manually**

**Checking Running Containers**
Run the following command to see active containers:
```sh
docker ps
```
Identify the container where MySQL is running. The backup will be taken from this container.

**Logging into the Remote-Host Container**

`remote-host`: container

```sh
docker exec -it remote-host /bin/sh
```

**Running the MySQL Dump Command**
```sh
mysqldump -u root -h dh_host -p test_db > /tmp/db.sql
```
Enter the MySQL root password when prompted.
```sh
1234
```

**Verifying the Backup**
```sh
cat /tmp/db.sql
```
Ensure the backup file contains the expected database content.

![Image](images/backup_and_upload_it_manually_to_s3_1.png)

**2. Configuring AWS CLI for Authentication**

**Setting Environment Variables**
![Image](images/backup_and_upload_it_manually_to_s3_2.png)
Set **AWS authentication credentials** using **environment variables**:
```sh
export AWS_ACCESS_KEY_ID=<your-access-key-id>
export AWS_SECRET_ACCESS_KEY=<your-secret-access-key>
```
![Image](images/backup_and_upload_it_manually_to_s3_3.png)

**3. Uploading the Backup to S3**

**Using AWS CLI to Upload the File**

**`s3-bucket-name`**: jenkins-mysql-backup
```sh
aws s3 cp /tmp/db.sql s3://jenkins-mysql-backup/db.sql
```
![Image](images/backup_and_upload_it_manually_to_s3_4.png)

**Verifying the Upload**
1. Navigate to the AWS S3 console.
2. Open the specified bucket.
3. Confirm that `db.sql` appears in the bucket.

![Image](images/backup_and_upload_it_manually_to_s3_5.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 7. Automate the backup and upload process with a shell script

This guide covers automating the MySQL backup process and uploading it to AWS S3 using a shell script. The script dynamically sets database parameters and timestamps the backups for better organization.

**Steps to Automate MySQL Backup**

**1. Create the Shell Script**
Log in to the remote host and create a new script file:
```bash
nano /tmp/script.sh
```
Add the following content:
```bash
#/bin/bash

# Get the current time in HH-MM-SS format
DATE=$(date +%H-%M-%S)

# Define the backup file name with timestamp
BACKUP=db-$DATE.sql

# Assign script arguments to variables
DB_HOST=$1        # Database host (passed as the first argument)
DB_PASSWORD=$2    # Database password (passed as the second argument)
DB_NAME=$3        # Database name (passed as the third argument)
AWS_SECRET=$4     # AWS Secret Access Key (passed as the fourth argument)
BUCKET_NAME=$5    # AWS S3 bucket name (passed as the fifth argument)

# Perform the MySQL database backup and store it in the /tmp directory
mysqldump -u root -h $DB_HOST -p$DB_PASSWORD $DB_NAME > /tmp/$BACKUP && \

# Export AWS credentials (Access Key ID is hardcoded; Secret Key is passed as an argument)
export AWS_ACCESS_KEY_ID=AKIAJRWZWY3CPV3F3JPQ && \
export AWS_SECRET_ACCESS_KEY=$AWS_SECRET && \

# Print a message indicating that the upload is starting
echo "Uploading your $BACKUP backup" && \

# Upload the backup file to the specified S3 bucket
aws s3 cp /tmp/$BACKUP s3://$BUCKET_NAME/$BACKUP
```

**2. Make the Script Executable**

```bash
chmod +x /tmp/script.sh
```

**Schedule the Script with Cron (Optional-Suggestion)**

To automate backups, add the script to crontab:
```bash
crontab -e
```
Add the following line to run it daily at midnight:
```bash
0 0 * * * /tmp/script.sh db_host 1234 testdb
```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 8. Learn how to manage sensitive information in Jenkins (Keys, Passwords)

**Introduction**
When working with Jenkins, it is essential to securely manage sensitive information such as passwords, API keys, and secret keys. Exposing these values in scripts or configuration files can lead to security risks. In this guide, we will walk through the process of managing sensitive information using Jenkins credentials.

**Identifying Sensitive Information**
In our script, we currently have two sensitive pieces of information:
- **AWS Secret Key**
- **Database Password**

To properly manage this data, we will use Jenkins Credentials to store and access them securely.

**Storing Credentials in Jenkins**

1. **Navigate to Credentials Management:**
   - Open Jenkins.
   - Click on **Manage Jenkins** > **Manage Credentials**.
   - Select **Jenkins** under the Credentials store.
   - Click on **Global credentials (unrestricted)**.


2. **Adding MySQL Password as a Secret Text:**
   - Click **Add Credentials**.
   - Select **Secret text** as the credential type.
   - In the **ID** field, enter `MYSQL_PASSWORD`.
   - Copy the database password from your configuration file (e.g., `1234`) and paste it into the **Secret** field.
   - Click **OK** to save the credential.

![Image](images/sensitive_information_in_jenkins_1.png)

3. **Adding AWS Secret Key as a Secret Text:**
   - Click **Add Credentials** again.
   - Select **Secret text** as the credential type.
   - In the **ID** field, enter `AWS_SECRET_KEY`.
   - Copy the AWS Secret Access Key provided by Amazon and paste it into the **Secret** field.
   - Click **OK** to save the credential.

![Image](images/sensitive_information_in_jenkins_2.png)


![Image](images/sensitive_information_in_jenkins_3.png)

**Benefits of Using Jenkins Credentials**
- **Security:** Credentials are encrypted and stored securely in Jenkins.
- **Access Control:** Only authorized users can access or modify credentials.
- **Automation:** Credentials can be easily integrated into pipelines without exposing them in scripts.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

## Section 7: Jenkins & Security

### 1. Intro - Learn how to Enable/Disable Login in Jenkins

Learn how to enable or disable login security in Jenkins to control authentication and access to jobs.

**Overview**

Security is a crucial aspect of Jenkins, especially for enterprises and applications. Controlling access to Jenkins ensures that only authorized users can manage jobs and configurations.

By default, Jenkins requires users to log in with a username and password. However, it is possible to disable login security, which allows unrestricted access to Jenkins. This guide will show you how to enable and disable login security in Jenkins.

**Steps to Disable Login Security**

1. Open **Manage Jenkins**.
2. Navigate to **Configure Global Security**.
3. Uncheck **Enable security**.
4. Click **Save**.
![Image](images/disable_login_in_jenkins.png)
5. Open an incognito window and go to `jenkins.local`.
6. You will notice that Jenkins no longer requires login credentials.

**⚠ Warning**

Disabling security allows anyone with access to the Jenkins server to perform any action, including deleting jobs and modifying configurations. This is **not recommended** for production environments.

**Steps to Enable Login Security**

1. Open **Manage Jenkins**.
2. Go to **Configure Global Security**.
3. Check **Enable security**.
4. Select **Jenkins database** for authentication.
5. Ensure that **Logged-in users can do anything** is selected.
6. Click **Save**.

![Image](images/enable_login_in_jenkins.png)

7. Open an incognito window and visit `jenkins.local`.
8. Jenkins will now require login credentials.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 2. Allow users to sign up

This guide explains how to allow users to register themselves in Jenkins. By enabling this option, users will see a **Sign up** option on the login screen.

**Steps to Enable User Sign Up**

1. Open **Manage Jenkins**.
2. Navigate to **Configure Global Security**.
3. Under **Security Realm**, check **Allow users to sign up**.
4. Click **Save**.

![Image](images/allow_users_to_sign_up_1.png)

5. Open an incognito window and go to `jenkins.local`.
6. You will now see an option to **Sign up** and create a new account.

![Image](images/allow_users_to_sign_up_2.png)

**Creating a New Account**

1. Click **Sign up**.
2. Enter the following details:
   - **Username**
   - **Full Name**
   - **Email Address**
   - **Password**
3. Click **Create an account**.
4. The new account will be created and, by default, assigned **admin** privileges.

![Image](images/allow_users_to_sign_up_3.png)

**⚠ Security Warning**

By default, new accounts created this way have **admin privileges**, which means they can:
- **Access** all jobs
- **Delete** projects
- **Modify** configurations

If your Jenkins server is publicly accessible, unauthorized users can create accounts and gain full control over your system.

**Steps to Disable User Sign Up**

1. Open **Manage Jenkins**.
2. Go to **Configure Global Security**.
3. Uncheck **Allow users to sign up**.
4. Click **Save**.

![Image](images/allow_users_to_sign_up_4.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 3. Install a powerful security plugin

Jenkins provides security features by default, but additional plugins can enhance its capabilities. This guide explains how to install and configure the **Role-based Authorization Strategy** plugin for better security management.

**Steps to Install the Security Plugin**

1. Open **Manage Jenkins**.
2. Navigate to **Manage Plugins**.
3. Click on the **Available Plugins** tab.
4. Use the filter box to search for **Role-based Authorization Strategy**.
5. Select the plugin and click **Download without restart**.
6. Click **Restart Jenkins when installation is complete**.
7. Wait for the installation to finish.

![Image](images/security_plugin_1.png)

**Verify Installation**

1. Go to **Manage Jenkins**.
2. Open **Manage Plugins**.
3. Switch to the **Installed** tab.
4. Search for **Role-based Authorization Strategy** to confirm its installation.

![Image](images/security_plugin_2.png)

**Configure the Plugin**

1. Go to **Manage Jenkins**.
2. Open **Configure Global Security**.
3. Under **Authorization**, select **Role-based Strategy**.
4. Click **Save**.

![Image](images/security_plugin_3.png)

5. After saving, a new section called **Manage and Assign Roles** will appear.

![Image](images/security_plugin_4.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

**6. Create users manually in the Jenkins DB**

This guide explains how to manually create users in Jenkins when sign-up is disabled.

**Steps to Create a User Manually**

1. **Go to Manage Jenkins**
   - Navigate to `Manage Jenkins`.
   - Scroll down to `Manage Users`.

![Images](images/create_users_manually_1.png)

2. **Create a New User**
   - Click `Create User`.

     ![Images](images/create_users_manually_2.png)

   - Fill in the details:
     - Username: `tom`
     - Password: `1234`
     - Full Name: `Tom`
     - Email: `tom@tom.com`
   - Click `Create User`.

     ![Images](images/create_users_manually_3.png)

3. **Verify the User in the Database**
   - The new user should appear under `Manage Users`.
   - It will indicate that the user is stored in `Jenkins' own database`.

4. **Test the New User Login**
   - Open an incognito browser tab.
   - Go to `jenkins.local`.
   - Log in with `tom` and password `1234`.
   - Notice that access **is denied**.

5. **Understanding User Restrictions**
   - Unlike users created via sign-up, manually created users have no permissions by default.
   - **This is due** to the `Role-based Authorization Strategy plugin`.

6. **Granting User Permissions**
   - Go to `Manage Jenkins` > `Configure Global Security`.
   - Assign roles and permissions to allow the user to perform specific actions.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 4. Ever heard about roles? Let's create a Read Only role!

This guide will walk you through the process of creating a **Read-Only Role** in Jenkins. Roles in Jenkins define the permissions a user has within the system. By following these steps, you will successfully create a role with read-only permissions.

**Prerequisites**
- A running instance of **Jenkins**
- Administrator access to **Manage Jenkins** settings
- **At least one user account** without assigned roles (e.g., `Ricardo` or `Tom`)

**Steps to Create a Read-Only Role**

**1. Open Jenkins Management Panel**
1. Log in to **Jenkins** with **an administrator account**.
2. Navigate to **Manage Jenkins**.
3. Scroll down and select **Manage and Assign Roles**.

![Image](images/create_a_read_only_role.png)

**2. Manage Roles**
1. Click on **Manage Roles**.
2. Locate the existing roles; you should see an **admin** role with full permissions.

![Image](images/create_a_read_only_role_1.png)

**3. Add a New Role**
1. Click on the **Add** button to create a new role.
2. Enter **a name for the role,** such as `read-only`.
3. **Select the permissions** for this role:
   - Check only **Read** **permissions**.
   - Ensure that **the role does not have permissions** to `administer, create, delete, or update` **configurations**.

![Image](images/create_a_read_only_role_2.png)

**4. Save the Role**
1. Scroll down and click **Save**.
2. The new **Read-Only Role** is now created.

**5. Assign the Role to Users**
1. Navigate to **Assign Roles**.
2. Locate the users (e.g., `Ricardo`, `Tom`) who need `read-only` access.
3. Assign them the **Read-Only Role**.
4. Click **Save** to apply changes.

![Image](images/create_a_read_only_role_3.png)

**Verification**
- Open an **Incognito Tab** and try logging in as a user with the new role.
- Ensure that the user can only read content and does not have permissions to modify Jenkins configurations.

**6. Modify Role Permissions for Job Viewing**

1. Return to **Manage Jenkins** > **Manage and Assign Roles**.
2. Click on **Manage Roles**.
3. Locate the **Read-Only Role**.
4. Under the **Job** section, check the **Read permission**.
5. Click **Save**.

![Image](images/create_a_read_only_role_4.png)

**7. Confirm Job Visibility**

1. Open the **Incognito Tab** and refresh Jenkins.
2. `tom` should now see the list of jobs but not modify them.
3. Clicking on a **job** will confirm that **no delete**, **configure**, **or build** options `are available`.

![Image](images/create_a_read_only_role_5.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 5. Create a role to execute jobs, and assign that role to your user

This guide explains how to create a **Build Role** in Jenkins that allows users to execute jobs while restricting their ability to create, delete, or modify jobs.

**Prerequisites**
- A **Jenkins** instance with role-based authorization configured
- Administrator access to **Manage Jenkins**
- At least one user account (e.g., `Ricardo` or `Tom`)

**Steps to Create and Assign a Build Role**

**1. Navigate to Manage Roles**
1. Log in to **Jenkins** with an administrator account.
2. Go to **Manage Jenkins**.
3. Scroll down and select **Manage and Assign Roles**.
4. Click on **Manage Roles**.

**2. Create a New Execution Role**
1. Click **Add** to create a new role.
2. Enter a name for the role, such as `execution`.
3. Ensure that the **Overall Read** permission is checked to prevent access errors.

![images](images/create_a_role_to_execute_jobs_1.png)

4. Navigate to the **Jobs** section.
5. Check **Read** and **Build** permissions.
6. Click **Save**.

![images](images/create_a_role_to_execute_jobs_2.png)

**3. Assign the Execution Role to a User**
1. Click on **Assign Roles**.
2. Locate the user (e.g., `Tom`).
3. Assign the **Execution Role** to the user.
4. Click **Save**.

![images](images/create_a_role_to_execute_jobs_3.png)

**4. Verify Role Assignment**
1. Open an **Incognito Tab**.
2. Navigate to `jenkins.local` and log in as `Tom`.
3. Go to any job and check if the **Build with Parameters** button is available.
4. Click **Build** and confirm that the job executes successfully.

![images](images/create_a_role_to_execute_jobs_4.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 6. Learn how to restrict Jobs to users using Project Roles

This guide explains how to restrict certain users to specific jobs in Jenkins using **Project Roles**. A Project Role allows administrators to **grant permissions based on patterns**, ensuring users can only access jobs that match predefined criteria.

**Creating a Project Role**

1. **Navigate to Role Management**
   - Go to `Manage Jenkins`.
   - Click on `Manage and Assign Roles`.
   - Select `Manage Roles`.

2. **Create a Global Role for Developers**
   - Enter the name of the new role (e.g., `dev`).
   - Click `Add`.
   - Assign the `Overall Read` permission to enable login.
   - Save the changes.

![images](images/creating_a_project_role_1.png)

3. **Define a Project Role**
   - In the `Project Roles` section, enter a new role name (e.g., `Ansible`).
   - Set a pattern (e.g., `Ansible-.*`) to match job names.
   - Click `Add`.

![images](images/creating_a_project_role_2.png)

   - Assign permissions such as:
     - `Read`: Allow viewing jobs.
     - `Build`: Allow executing jobs.
   - Save the changes.

![images](images/creating_a_project_role_3.png)

**Assigning Project Roles to Users**

1. **Navigate to Assign Roles**
   - Go to `Manage Jenkins` > `Manage and Assign Roles` > `Assign Roles`.
   - Ensure the user has the `dev` global role (for login access).

![images](images/creating_a_project_role_4.png)

2. **Bind Users to Project Roles**
   - Under `Item Roles`, find the created role (e.g., `Ansible`).
   - Add the user (e.g., `Tom`).
   - Assign the project role to the user.
   - Save the changes.

![images](images/creating_a_project_role_5.png)

**Testing Role Restrictions**
1. Open an incognito tab and log in as the user (`Tom`).
2. Verify that the user can:
   - See only jobs starting with "`Ansible`".
   - **Execute** jobs if the `Build` **permission is assigned**.
3. Ensure that unauthorized jobs are not visible.

![images](images/creating_a_project_role_6.png)

**Expanding Access to Additional Jobs**
1. **Create Another Project Role**
   - Navigate to `Manage Roles`.
   - Add a new role (e.g., `Backup`).
   - Set the pattern to `Backup-.*`.
   - Assign appropriate permissions.
   - Save the changes.

![images](images/creating_a_project_role_7.png)

1. **Assign the New Role to the User**
   - Go to `Assign Roles`.
   - Bind the user to the `Backup` role.
   - Save the changes.
   
   ![images](images/creating_a_project_role_8.png)

   - Test access to backup-related jobs.
   ![images](images/creating_a_project_role_9.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

## Section 8: Jenkins Tips & Tricks

### 1. Global environment variables in Jenkins

This guide explains the global environment variables available in Jenkins by default and how to use them in your jobs.

**Viewing Available Environment Variables**

To find the list of available environment variables:
1. Go to Google and search for **Jenkins Environment Variables Wiki**.
2. Look for the official Jenkins documentation on environment variables.
3. There, you will find a table listing all the available variables.

https://wiki.jenkins.io/JENKINS/Building+a+software+project


**Example: Using Environment Variables in a Jenkins Job**

Let's create a simple Jenkins freestyle job that prints environment variables.

**Steps:**

1. **Create a new job**: Name it `ENV` and select **Freestyle project**.
2. **Add a build step**:
   - Choose **Execute shell**.
   - Add the following script:
     ```bash
     echo "BUILD NUMBER FOR THIS $BUILD_NUMBER"
     echo "BUILD ID IS $BUILD_ID"
     echo "BUILD URL IS $BUILD_URL"
     echo "JOB NAME IS $JOB_NAME"
     ```
3. **Save and build the job**.
![images](images/global_environment_variables_1.png)

**Console Output Example:**

After running the job, check the console output to see the values:
```
BUILD NUMBER FOR THIS 1
BUILD ID IS 1
BUILD URL IS http://your-jenkins-server/job/ENV/1/
JOB NAME IS ENV
```
![images](images/global_environment_variables_1.png)

**Use Cases**

- **Notifications**: Use these variables in emails or Slack messages to report job status.
- **Logging**: Include them in logs to track executions.
- **Conditional Execution**: Use them in scripts to handle different scenarios.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 2. Create your own custom global environment variables

In this guide, you'll learn how to create your own global environment variables in Jenkins. By default, Jenkins provides built-in environment variables such as execution number, job name, and build URL. However, **you may need to define custom global variables** to be used across all jobs.

**Steps to Create Custom Global Environment Variables**

1. **Navigate to Manage Jenkins**
   - Open Jenkins and go to **Manage Jenkins > Configure System**.
   - Scroll down and look for the **Global Properties** section.
   - Check the box for **Environment Variables**.
   - Click on the **Add** button to create new variables.
   - Example variables:
     - `NAME_OF_COURSE = Jenkins-course`
     - `COUNTRY = Colombia`
   - Click **Save** to apply the new environment variables.

![images](images/custom_global_environment_variables_1.png)

**Using Custom Environment Variables in a Job**

1. **Modify an Existing Job**
   - Open the job where you want to use the variables.
   - Click on **Configure**.
   - Add an **Execute Shell** step and use `echo` to print the variables:
     
   ```bash
   echo "$NAME_OF_COURSE"
   echo "$COUNTRY"
   ```

    ![images](images/custom_global_environment_variables_2.png)

   - Click **Save**.
   - Click **Build Now** to execute the job.
    ![images](images/custom_global_environment_variables_3.png)

**Why Use Custom Global Environment Variables?**

- Store **common configuration values** like server names or API keys.
- **Avoid hardcoding** values in multiple jobs.
- Ensure consistency across Jenkins pipelines.
- Simplify **maintenance and updates.**

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 3. Modify the Jenkins URL
 
This guide explains how to **modify the Jenkins URL** `to use a DNS instead of an IP address`. This is essential for ensuring that Jenkins can be accessed using a proper domain name rather than an IP address, which might change over time.

**Steps to Modify the Jenkins URL**
 
1. Open Jenkins and go to `Manage Jenkins`.
2. Click on `Configure System`.
3. Scroll down to the `Jenkins Location` section.
4. Locate the `Jenkins URL` field.
5. By default, the field may contain an IP address.
6. Change the `Jenkins URL` field to your desired domain, such as:
   ```
   http://jenkins.local:8080/
   ```
7. **Save Changes**
8. Click `Save` to apply the new settings.
9. Navigate back to `Manage Jenkins` to verify that the error has been resolved.

**Configure the Local DNS (Windows)**

Since `jenkins.local` is **not a real domain**, you need to configure your system to recognize it:

1. Open **Notepad** as Administrator.
2. Click `File` > `Open` and navigate to:
   ```
   C:\Windows\System32\drivers\etc\hosts
   ```
3. Select "All Files" in the file type dropdown and open the `hosts` file.
4. Add the following line at the **end of the file**:
   ```
   127.0.0.1   jenkins.local
   ```
5. Save the file and close Notepad.

**Restart Jenkins (Docker)**

If you are running Jenkins in a Docker container, restart it to apply the changes:

- If running with `docker run`:
  ```sh
  docker restart <jenkins_container_name>
  ```
- If running with `docker-compose`:
  ```sh
  docker-compose restart jenkins
  ```

**Access Jenkins with the New URL**
1. Open a web browser.
2. Navigate to `http://jenkins.local:8080/`.
3. Jenkins should now be accessible with the new URL.

**Benefits of Using a DNS for Jenkins**

- **Easier Access**: Users can access Jenkins using a domain name instead of an IP.
- **Consistency**: The URL remains the same even if the server's IP changes.
- **Better Integration**: Some plugins and integrations may require a proper DNS.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 4. Meet the Jenkins' cron: Learn how to execute Jobs automatically

**Why Use Cron in Jenkins?**

If you have **a job that needs to run at a specific time**, such as a daily backup at 1:00 AM, you don't want to manually trigger it. Instead, you can configure Jenkins to run the job automatically **using a cron expression.**

**Configuring a Cron Job in Jenkins**

**Step 1: Navigate to Job Configuration**
1. Open **Jenkins** in your browser.
2. Select `the job` you want to schedule.
3. Click **Configure**.

**Step 2: Enable Build Triggers**
1. Scroll down to the **Build Triggers** section.
2. Check the **Build periodically** option.
3. Enter a cron expression in the provided field.

![image](images/execute_jobs_automatically_1.png)

**Step 3: Save and Verify**
1. Click **Save**.
2. Check the **Next execution time** displayed by Jenkins.
3. Wait for the job to run automatically.

**Step 4: Verify Execution**
1. Navigate to **Build History**.
2. Click on a build.
3. Open **Console Output**.
4. Look for `Started by timer`, confirming automatic execution.

**Understanding Cron Expressions**
Jenkins uses a five-field cron syntax:
```
MINUTE HOUR DAY_OF_MONTH MONTH DAY_OF_WEEK
```

For example, to schedule a job at 1:00 AM every day:
```
0 1 * * *
```
This means:
- `0` → At the 0th minute (start of the hour)
- `1` → At 1 AM
- `*` → Every day of the month
- `*` → Every month
- `*` → Every day of the week


<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 5. Troubleshooting: Githooks throwing 403 forbidden errors?

There's a chance your githooks won't trigger correctly with 403 erros. This is due to a jenkins major upgrade, which modified something called CSRF in Jenkins, that protects you against DOS attacks.

Info:

https://jenkins.io/doc/upgrade-guide/2.176/#SECURITY-626

Resolution:

* Install a plugin named Strict Crumb Issue

* Go to Manage Jenkins -> Configure Global Security -> CSRF Protection.

* Select Strict Crumb Issuer.

* Click on Advanced.

* Uncheck the Check the session ID box.

* Save it.

It should look like this:

![images](images/csrf_in_jenkins.png)

You can also check this question in the QA space, which is very informative: 8273042 

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 6.Trigger your Jobs from Bash Scripts (No parameters)

This guide explains how to `trigger a Jenkins job` from a script when the job does **not** require parameters.

**Steps to Trigger a Job**

**1. Copy the Job Execution URL**

1. Open **Jenkins** and navigate to the **job** you want to trigger.
2. Click on **Build Now**.
3. Right-click on the button and select **Copy Link Address**.
4. Paste the URL into a text editor – this is the job execution endpoint.

**Example**   
```shell
http://localhost:8080/job/<name_job>/build?delay=0sec
```

**2. Enable CSRF Protection & Generate a Crumb**

Jenkins requires a security **crumb token** to prevent **Cross-Site Request Forgery **(CSRF) attacks. To retrieve it:

1. Go to **Manage Jenkins** → **Configure Global Security**.
2. Scroll down to **CSRF Protection**.
3. Ensure it is enabled.

![images](images/trigger_your_jobs_1.png)

5. Generate a crumb using the following command:

```bash
CRUMB=$(curl -s -u "jenkins_user:your_password" "http://your-jenkins-server/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,":",//crumb)")
echo "Crumb: $CRUMB"
```

This saves the crumb into a variable that **will be used for authentication**.

**3. Set Up Hostname Resolution (Optional)**
If your system does not recognize `jenkins.local`, add it to `/etc/hosts`:

```bash
sudo vi /etc/hosts
```
![images](images/trigger_your_jobs_2.png)

Add the following line:

```
127.0.0.1    jenkins.local
```
![images](images/trigger_your_jobs_3.png)

Save and exit.

```
curl jenkins.local:8080
```
![images](images/trigger_your_jobs_4.png)

![images](images/trigger_your_jobs_5.png)

![images](images/trigger_your_jobs_6.png)

**4. Create the Bash Script**

1. Create a new script file:
   ```bash
   nano crumb.sh
   ```
2. Add the following content:
   ```bash
   #!/bin/bash
   
   # Retrieve the Jenkins crumb for CSRF protection
   crumb=$(curl -u "jenkins:1234" -s 'http://jenkins.local:8080/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,":",//crumb)')

   # Trigger a Jenkins job using the retrieved crumb
   curl -u "jenkins:1234" -H "$crumb" -X POST "http://jenkins.local:8080/job/ENV/build?delay=0sec"
   ```

![images](images/trigger_your_jobs_7.png)

3. Save and exit (`CTRL+X`, then `Y`, then `ENTER`).
4. Grant execution permissions:
   ```bash
   chmod +x crumb.sh
   ```

**5. Execute the Script**

Run the script to trigger the job:

```bash
./crumb.sh
```

**6. Verify the Execution**

1. Open Jenkins and navigate to your job.
2. Check if **a new build has started**.
3. Open the **Console Output** of the job to confirm execution.

**Before**
![images](images/trigger_your_jobs_8.png)

**After**
![images](images/trigger_your_jobs_9.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 7.Trigger your Jobs from Bash Scripts (With Parameters)

1. Create a new script file or reuse:
   ```bash
   nano crumb.sh
   ```
2. Add the following content:
   ```bash
   #!/bin/bash
   
   # Retrieve the Jenkins crumb for CSRF protection
   crumb=$(curl -u "jenkins:1234" -s 'http://jenkins.local:8080/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,":",//crumb)')

   # Trigger a Jenkins job using the retrieved crumb
   curl -u "jenkins:1234" -H "$crumb" -X POST  http://jenkins.local:8080/job/backup-to-aws/buildWithParameters?MYSQL_HOST=db_host&DATABASE_NAME=testdb&AWS_BUCKET_NAME=jenkins-mysql-backup
   ```
3. Save and exit (`CTRL+X`, then `Y`, then `ENTER`).
4. Grant execution permissions:
   ```bash
   chmod +x crumb.sh
   ```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

## Section 9: Jenkins & Email

### 1.Install a Mail Plugin
1. **Check if the Mailer Plugin is Already Installed**
    - When setting up Jenkins, if you selected **Install suggested plugins**, the Mailer plugin might already be installed.
    - To verify this, navigate to:
      - **Manage Jenkins** > **Manage Plugins**
      - Go to the **Installed** tab
      - Search for `Mailer`
      - If it appears in the list, **the plugin is already installed**.

![images](images/jenkins_email_1.png)

2. **Install the Mailer Plugin**
    - If the plugin is not found in the **Installed** section:
      - Go to **Manage Jenkins** > **Manage Plugins**
      - Open the **Available** tab
      - Search for `Mailer`
      - If found, select it and install the plugin
 
<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 2. Integrate Jenkins and AWS Simple Email Service

In this guide, we will learn how to integrate **AWS Simple Email Service (SES)** with Jenkins.

**Prerequisites**

- A Jenkins instance already set up
- An AWS account

**Steps to Integrate Jenkins with AWS SES**

**1. Log in to AWS and Access SES**

- Sign in to your AWS account: https://aws.amazon.com/console/
- Click on the **Services** tab and search for **SES (Simple Email Service)**.
- Click on **SES** to access the service.

![images](images/jenkins_email_2.png)

![images](images/jenkins_email_3.png)

**2. Verify a Domain or Email Address**
- To send emails, AWS SES requires verification of a `domain` or `an email address`.
- You can verify:
  - A domain, if available.
  - An email address, if you don’t have a domain.
- Click on **Verify a new email address**.
- Enter your email and click **Verify**.

![images](images/jenkins_email_4.png)

- Check your email for a verification message from AWS and **click on the provided link**.
- Refresh the AWS SES console to **confirm verification**.

![images](images/jenkins_email_5.png)

**3. Configure Jenkins for Email Notifications**
- In Jenkins, navigate to **Manage Jenkins** > **Configure System**.
- Scroll down to **Email Notification**.
- Click **Advanced** and locate the **SMTP Server** field.
- Retrieve the `SMTP server details` from `AWS SES`:
  - In AWS SES, go to **SMTP Settings**.
  - Copy the **SMTP server name** and paste it into Jenkins.
![images](images/jenkins_email_6.png)


**4. Set Up SMTP Authentication**
- Enable **Use SMTP Authentication**.
- Create SMTP credentials in AWS SES:
  - Click on **Create SMTP Credentials**.
  - Enter a name (e.g., `jenkins-test-mail`), then click on **Create** button and download credentials.
![images](images/jenkins_email_7.png)
  - Copy the **username** and **password** and paste them into Jenkins.
![images](images/jenkins_email_8.png)

**5. Configure Connection Security and Ports**
- Enable **Use SSL**.
- Retrieve available SMTP ports from AWS SES.
- Use **Port 465** and enter it in Jenkins.
- Set a **Reply-To Address** (your verified email).

![images](images/jenkins_email_9.png)

**6. Test Configuration**
- Ensure the **System Admin Email** field contains your verified email.
- Scroll down and test the configuration by sending a test email.
- Check your email inbox (or spam folder) for the test email.
- If blocked, mark it as **Not Spam**.

**7. Troubleshooting**
- Ensure your machine can access **Port 465**.
- If the email is not received, `check` **your spam folder**.
- If using an office network, confirm that the port is not blocked.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 3. Integrate Jenkins and Gmail

**Prerequisites**

- A Jenkins instance already set up
- A Gmail account

**Steps to Integrate Jenkins with Gmail**

**1. Configure SMTP Settings in Jenkins**
- Navigate to **Manage Jenkins** > **Configure System**.
- Locate the **SMTP Configuration** section.
- Use the following settings:
  - **SMTP Server:** `smtp.gmail.com`
  - **Use SMTP Authentication:** Enabled
  - **Username:** Your Gmail email address
  - **Password:** Your Gmail account password
  - **Use SSL:** Enabled
  - **SMTP Port:** `465`

![images](images/jenkins_and_gmail_1.png)

**2. Enable Less Secure Apps in Gmail**
- Go to [Google Account Security](https://myaccount.google.com/security).
- Scroll down to **Less secure app access**.
- Enable the option to allow less secure apps to access your Gmail account.

![images](images/jenkins_and_gmail_2.png)

**3. Test Configuration**
- In Jenkins, scroll down to the **Test Configuration** section.
- Enter your email address in the recipient field.
- Click **Test Configuration** to send a test email.
- Check your inbox to confirm that the email was sent successfully.

![images](images/jenkins_and_gmail_3.png)

**4. Troubleshooting**
- Ensure that **Less secure app access** is enabled in your Gmail account.
- Verify that your ISP or office network does not block **Port 465**.
- Check the spam folder if the test email does not appear in your inbox.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 4. Integrating Email Notifications into Jenkins Jobs

**Step 1: Access Job Configuration**
1. Navigate to **Jenkins Dashboard**.
2. Open the **job** (e.g., `ENV` job) for which you want to enable email notifications.
3. Click on **Configure**.
4. Scroll down to the **Post-build Actions** section.

**Step 2: Add Email Notifications**
1. Click on **Add post-build action**.
2. Select **Email Notification**.
3. In the configuration panel:
   - Check **Send email for every unstable build**.
   - Check **Send emails to individuals who broke the build**.
   - Enter the recipient email address in the **Recipient List**.

![image](images/email_notifications_1.png)

**Step 3: Test Email Notification on Failure**
1. Modify the build to force a failure:
   - Add an invalid command such as `echo1` (**a non-existent command**).
   - Save the configuration.
![image](images/email_notifications_2.png)
2. Run the build.
3. The build should fail, triggering an email notification.

![image](images/email_notifications_3.png)

4. Check your inbox for a Jenkins notification email indicating the failure.

![image](images/email_notifications_4.png)

**Step 4: Restore the Job to Normal**
1. Remove the `invalid command` from the job configuration.
2. Save the job and execute it again.
3. The build should succeed, and Jenkins will send a **recovery notification** indicating that the job is back to normal.
4. If the job runs successfully afterward, no further notifications will be sent.

![image](images/email_notifications_5.png)

**Key Takeaways**
- Jenkins sends notifications for failures and recoveries but not for successful builds.
- Ensure the **SMTP settings** are correctly configured in Jenkins to enable email notifications.
- Check your spam folder if you do not receive the notification.

This setup allows you to monitor job failures efficiently, ensuring you are notified promptly when an issue occurs.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

## Section 10: Jenkins & Maven

### 1. Install the Maven Plugin

1. Navigate to **Manage Jenkins** > **Manage Plugins**.
2. Go to the `Available Plugins` tab and search for `Maven`.
3. Select **Maven Integration Plugin**, then click **Install** without restart.

![imagen](images/jenkins_maven_1.png)

4. Once installed, restart Jenkins.
5. Verify installation in **Manage Plugins** > Installed by searching for **Maven**.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 2. Install the GIT Plugin

1. Go to **Manage Jenkins** > **Manage Plugins**.
2. Check the `Installed` tab and search for **Git**.
3. If `Git Plugin` and `Git Client Plugin` are listed, they are already installed.
4. If not, go to the `Available Plugins` tab, search for **Git**, and install the necessary plugins.
![imagen](images/git_plugin_1.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 3. Learn how to clone a GIT/GITHUB repository from Jenkins
 
**1. Create a New Jenkins Job**

1. Open Jenkins and click on **New Item**.
2. Enter a job name (e.g., `maven-job`).
3. Select **Freestyle Project** and click **OK**.

**2. Configure Source Code Management (SCM)**
1. Under the **Source Code Management** section, select **Git**.
2. Copy the repository URL from GitHub and paste it into the **Repository URL** field.
```
https://github.com/jenkins-docs/simple-java-maven-app
```
3. (Optional) Click **Advanced** to specify a different branch (default is `master`).
4. No credentials are needed for public repositories.
5. Click **Save**.

![imagen](images/clone_git_repository_1.png)


**3. Build the Job**
1. Click **Build Now** to start the job.
2. Navigate to **Build History** → **Console Output**.
3. Verify that the repository was successfully cloned.

![imagen](images/clone_git_repository_2.png)

**4. Locate the Cloned Repository**
1. Jenkins clones repositories into a **workspace**.
2. To find the workspace, run the following command:
   ```sh
   docker exec -ti jenkins bash
   cd /var/jenkins_home/workspace
   ls -l
   ```
   ![imagen](images/clone_git_repository_3.png)
   ![imagen](images/clone_git_repository_4.png)

3. Locate your job folder (e.g., `maven-job`) and enter it:
   ```sh
   cd maven-job
   ls -l
   ```
4. You should see all the cloned files matching the GitHub repository structure.

![imagen](images/clone_git_repository_5.png)

To see the hidden files.
   ```sh
   ls -la
   ```

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 4. Learn how to build a JAR using maven
**Prerequisites**
- Jenkins installed and running.
- **Maven plugin** installed in Jenkins.
- A **Git repository** containing **a Maven project**.

**Step 1: Configure Maven in Jenkins**
1. Navigate to **Manage Jenkins > Global Tool Configuration**.
2. Locate the **Maven** section and click **Add Maven**.
3. Provide a name (e.g., `jenkins-maven`).
4. Select the **latest Maven version**. (e.g: `3.9.2`)
5. Click **Save**.

![imagen](images/build_a_jar_using_maven_1.png)

**Step 2: Configure the Jenkins Job**
1. Open the existing **maven-job** or create a new one.
2. Navigate to **Configure**.
3. In the **Build** section, add a new build step:
   - Select **Invoke top-level Maven targets**.
   - Choose the Maven version configured earlier.
   - In the **Goals** field, enter:
     ```sh
     -B -DskipTests clean package
     ```
4. Click **Save**.

![imagen](images/build_a_jar_using_maven_2.png)

**Step 3: Run the Job**
1. Click **Build Now** to start the job.
2. Navigate to **Build History > Console Output** to monitor progress.
3. Jenkins will:
   - Clone the latest version of the Git repository.
   - Download required Maven dependencies (only on the first run).
   - Build the JAR file.

![imagen](images/build_a_jar_using_maven_3.png)

**Step 4: Locate the Built JAR**
- The resulting JAR file is stored in the **workspace**:
  ```sh
  workspace/maven-job/target/
  ```
- Navigate to the **target** directory to find the generated JAR.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 5. Learn how to test your code

1. Open the existing **maven-job**.
2. Navigate to **Configure**.
3. In the **Build** section, add **a new build step**:
   - Select **Invoke top-level Maven targets**.
   - Choose the Maven version configured earlier.
   - In the **Goals** field, enter:
     ```sh
     test
     ```
4. Click **Save**.

![imagen](images/test_your_code_1.png)
![imagen](images/test_your_code_2.png)
![imagen](images/test_your_code_3.png)


<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 6. Deploying Your JAR Locally
 
Before deploying, ensure your application passes all tests. If a test fails, the job should stop, preventing the deployment of a faulty JAR.

**1. Add a Shell Step in Jenkins**
1. Navigate to **Configure** for the Jenkins job.
2. Add a new **Build Step**.
3. Select **Execute Shell**.
4. Enter the following commands:

```sh
echo "******** Deploying JAR ********"
java -jar /var/jenkins_home/workspace/maven-job/target/my-app-1.0-SNAPSHOT.jar
echo "Deployment completed."
```
5. Save the configuration.

![imagen](images/deploying_your_jar_1.png)

**2. Execute the Job**
1. Click **Build Now**.
2. Navigate to the console output to verify the deployment.

**3. Validate Deployment**
If successful, the console output should display:

```sh
Hello World!
```
![imagen](images/deploying_your_jar_2.png)

This confirms the JAR was executed successfully within the Jenkins container.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 7. Display the result of your tests using a graph

**1. Locate the Test Report**

Maven generates a test report in an XML file stored in:

![images](images/tests_using_a_graph_1.png)
```
target/surefire-reports/*.xml
```

This XML contains detailed test results.

![images](images/tests_using_a_graph_2.png)

**2. Configure Jenkins to Publish Test Reports**

1. Navigate to **Configure** for the Jenkins job.
2. Add a **Post-Build Action**.
3. Select **Publish JUnit Test Report**.
4. Enter the following path in the report configuration:
```
target/surefire-reports/*.xml
```
5. Save the configuration.

![images](images/tests_using_a_graph_3.png)

**3. Generate the Test Results Graph**

1. Execute the job multiple times (at least five runs).
2. Go to the **Job Dashboard** in Jenkins.
3. Observe the **Test Result Trend** graph appearing.

![images](images/tests_using_a_graph_4.png)

The graph provides a visual representation of test trends over time, highlighting errors in red if they occur.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 8. Archive the last successful artifact

1. **Locate the JAR File:**
   - The JAR file is generated in `target/`.
   - Example: `target/app.jar`

2. **Configure Jenkins to Archive Artifacts:**
   - Go to **Post-Build Actions** → **Archive the Artifacts**.
   - Specify the artifact path:
     ```
     target/*.jar
     ```
   - Click on **Advanced** and select **Archive only if build is successful**.
   - Save and trigger a new build.

![images](images/archive_artifact_1.png)

3. **Verify Archived Artifacts:**
   - After `a successful build`, go to the Jenkins job page.
   - The **Last Successful Artifact** section will appear with a downloadable link to the JAR file.
 
![images](images/archive_artifact_2.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

### 9. Send Email notifications about the status of your maven project

**Prerequisites**
- A Jenkins instance running
- A configured Maven project in Jenkins
- An SMTP server set up in Jenkins for sending emails

**Steps to Configure Email Notifications**

**1. Configure Email Notifications in Jenkins**
1. Open Jenkins and navigate to your Maven project.
2. Click on **Configure**.
3. Scroll down to the **Post-build Actions** section.
4. Click on **Add post-build action** and select **Email Notification**.
5. Enter the recipient email address.
6. Select the options:
   - **Send email for every unstable build**
   - **Send separate emails to individuals who broke the build** (optional)
7. Click **Save**.

![images](images/send_email_notifications_1.png)

**2. Trigger a Failure to Test Email Notifications**
1. Modify the project to introduce an intentional error (e.g., an incorrect parameter in the build step).
2. Click **Build Now**.
3. The build will fail, and Jenkins will send an email notification with the error details.
4. Check your email inbox for the notification.

![images](images/send_email_notifications_2.png)

**3. Fix the Issue and Validate Successful Notification**
1. Remove the introduced error from the configuration.
2. Click **Build Now** again.
3. The build should now complete successfully.
4. Jenkins will send another email notifying that the build is back to normal.

![images](images/send_email_notifications_3.png)

**Benefits of Email Notifications**
- **Real-time Alerts:** Get notified immediately **when a build fails.**
- **Efficient Debugging:** Email contains logs and error details to quickly identify issues.
- **Automated Monitoring:** No need to manually check Jenkins dashboard.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

## Section 11: Jenkins & GIT
### 1. Create a Git Server using Docker

**Prerequisites**
- A virtual machine with at least **2 CPU cores** and **4GB RAM** (8GB+ recommended for better performance)
- **Docker** and **Docker Compose** installed
- **Access to modify the hosts file** on your local machine

**Step 1: Adjust Virtual Machine Resources**

Before running the GitLab container, ensure your virtual machine has sufficient resources:

1. Power off your virtual machine.
2. Open VirtualBox settings:
   - Navigate to **System → Base Memory** and assign **at least 4GB RAM** (8GB+ recommended).
   - Navigate to **System → Processor** and assign **at least 2 cores**.
3. Start the virtual machine and verify the configuration:
   ```sh
   cat /proc/cpuinfo | grep cores  # Should show at least 2 cores
   free -h  # Should show the assigned RAM
   ```
![images](images/git_server_1.png)

**Step 2: Create a GitLab Service Using Docker Compose**

1. Navigate to your Jenkins data folder at the same level as your `docker-compose.yml` file.
2. Search for the **official GitLab Docker image**:
   ```sh
   google "Docker GitLab"
   ```
3. Copy the **Docker Compose configuration** from the official documentation.

```sh
https://docs.gitlab.com/install/docker/installation/#install-gitlab-by-using-docker-compose
```

5. Open your `docker-compose.yml` file (`jenkins_git`) and add the following service:
   ```yaml
    services:
      jenkins:
        container_name: jenkins
        image: jenkins/jenkins:lts
        ports:
          - "8080:8080"
        volumes:
          - jenkins_home_data:/var/jenkins_home # Persist Jenkins data (configs, plugins, jobs)
        networks:
          - net # Define a custom Docker network
      remote_host:
        container_name: remote-host
        image: remote-host
        build:
          context: . # Define the build context ('Dockerfile' should be inside the 'centos7' directory)
        networks:
          - net
      db_host:
        container_name: db
        image: mysql:5.7
        environment:
          # Set the root password for MySQL
          MYSQL_ROOT_PASSWORD: "1234"  
        volumes:
          - db_data:/var/lib/mysql
        networks:
          - net

      git:
        container_name: git-server
        image: 'gitlab/gitlab-ce:latest'
        hostname: 'gitlab.example.com'
        ports:
          - '8090:80'
        volumes:
          - '/srv/gitlab/config:/etc/gitlab'
          - '/srv/gitlab/logs:/var/log/gitlab'
          - '/srv/gitlab/data:/var/opt/gitlab'
        networks:
          - net

    networks:
      net: # Define a custom Docker network to enable communication between containers

    # These volumes (jenkins_home_data and db_data) 
    # are managed by Docker and stored in its volume system
    volumes:
      jenkins_home_data: 
      db_data:
   ```

6. Save the file and start the GitLab server:
   ```sh
   docker-compose up -d
   ```

![images](images/git_server_2.png)

**Step 3: Monitor the GitLab Server Startup**

GitLab takes a few minutes to initialize:
`docker ps`: Verify the container is running

```sh
docker ps
```
![images](images/git_server_3.png)

`docker logs -f git-server`: Monitor startup logs
```sh
docker logs -f git-server
```
Wait until you see a message similar to:
```
 Chef Client finished...
 GitLab Reconfigured.
```
This indicates the server is ready.

![images](images/git_server_4.png)

**Step 4: Configure DNS to Access GitLab**
To access GitLab from a browser, update the **hosts file** on your local machine:

1. Open Notepad **as Administrator**.
2. Navigate to:
   ```
   C:\Windows\System32\drivers\etc\hosts
   ```
3. Add the following entry (replace `<VM_IP>` with your virtual machine's IP):
   ```
   <VM_IP> gitlab.example.com
   ```
4. Save the file.

![images](images/git_server_5.png)

**Step 5: Access GitLab from the Browser**
1. Open a web browser and go to:
   ```
   http://gitlab.example.com:8090
   ```
   or
   ```
   http://localhost:8090/
   ```
2. You will be prompted to set a new **root** password (minimum 8 characters).
3. Log in using:
   - **Username**: `root`
   - **Password**: The one you just set
4. Click **Sign In**.

Or
1. Use this command to set the root user:
```
docker exec -it git-server gitlab-rake "gitlab:password:reset"
```
![images](images/git_server_6.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

### 2. Create your first Git Repository

**1. Create a Group**

GitLab **groups** help organize multiple projects under a common namespace.

1. **Go to GitLab** and navigate to the **Groups** section.
2. Click on **Create Group**.
3. Enter a **name** for your group (e.g., `jenkins`).
4. GitLab will generate a URL for the group automatically.
5. Choose a **visibility level**:
   - **Private** (Only members can access)
   - **Internal** (Accessible to logged-in users)
   - **Public** (Accessible to everyone)
6. Select **Private** for now.
7. Click **Create Group**.

![image](images/create_your_first_git_repository_1.png)
![image](images/create_your_first_git_repository_2.png)
![image](images/create_your_first_git_repository_3.png)

**2. Create a Repository (Project)**

Now that you have a group, you can create projects (repositories) under it.

1. Inside your group, click on **New Project**.
2. Choose a **project name** (e.g., `maven`).
3. The URL will be generated as `jenkins/maven`.
4. Set the visibility level to **Private**.
5. Click **Create Project**.

![image](images/create_your_first_git_repository_4.png)

**3. Understanding GitLab Groups and Projects**

- The **group** (e.g., `jenkins`) serves as a container for multiple projects.
- The **repository** (e.g., `maven`) is a project under that group.
- You can create multiple projects within a group.
- You can also create multiple groups for better organization.

![image](images/create_your_first_git_repository_5.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

### 3. Create a Git User to Interact with Your Repository

**Creating a New User**
1. **Access the Admin Area**
   - Navigate to the GitLab **Admin Area**.
   ```
   http://localhost:8090/admin/users
   ```
   - Click on **Users**.
   - Click on **New User**.

![image](images/create_a_git_user_1.png)

2. **Fill in User Details**
   - Enter the **name** (e.g., `Ricardo`).
   - Enter a **username**.
   - Provide an **email address** (can be a fake email for now).
   - Scroll down and ensure the user is set as a **regular user**.
   - Click on **Create User**.

![image](images/create_a_git_user_2.png)

3. **Set a Password for the User**
   - Edit the newly created user.
   - Set a password with at least **8 characters** (e.g., `1234567812345678`).
   - Click **Save Changes**.

![image](images/create_a_git_user_3.png)
![image](images/create_a_git_user_4.png)

**Granting Repository Access to the User**
1. **Navigate to the Project**
   - Go to **Projects**.
   - Select the **Maven** project (created under the `Jenkins` group).

![image](images/create_a_git_user_5.png)
```
http://localhost:8090/admin/projects/jenkins/maven
```

2. **Manage Access**
   - Click on **Manage Access** (or **Project Members**).
   - Search for the user (`Ricardo`).
   - Assign **Maintainer** role (to allow branch creation and avoid permission errors).
   - Click **Add to Project**.

![image](images/create_a_git_user_6.png)
![image](images/create_a_git_user_7.png)

3. **Verify Permissions**
   - Go to the **Maven** project.
   - Click on **Settings** > **Members**.
   - Confirm that `Ricardo` has been added with the correct permissions.
![image](images/create_a_git_user_8.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

### 4. Upload the code for the Java App in your Repo

**1. Ensure the GitLab Container is Running**
Make sure GitLab is running in Docker before proceeding.  

**2. Navigate to the Project Directory**  
Open a terminal and move to the project folder:  

```sh
cd \jenkins_git\simple-java-maven-app
```
or download this repository and remove the `.git` directory:
```
https://github.com/jenkins-docs/simple-java-maven-app
```
**3. Initialize the Git Repository**

Initialize a Git repository:  

```sh
git init
```

**4. Add and Commit the Code**

Add all files to the repository and create the first commit:  

```sh
git add .
git commit -m "Initial commit"
```

**5. Set GitLab as the Remote Repository**

Add GitLab as a remote repository with the following command:  

```sh
git remote add origin http://localhost:8090/jenkins/maven.git
```

**6. Authenticate in GitLab**
- Before pushing the code, log in to GitLab with the previously created user.  
- Change the password on the first login if required.  

**7. Push the Code to GitLab**
- To upload the code from the `\jenkins_git\simple-java-maven-app` folder to GitLab, run:  

```sh
git push origin
```

**8. Verify the Upload in GitLab**
- Open GitLab in your browser.  
- Navigate to the repository and refresh the page to confirm that the files were successfully uploaded.

![image](images/upload_the_code_in_your_repo_1.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

### 5. Learn about Git Hooks

If you have never heard about Git hooks before, don't worry, but you must know that a **Git hook** is **like a trigger**.

For example, whenever someone pushes to any branch, **a trigger is activated**, and you can define what action should be performed.

For instance, whenever a developer pushes to your master branch, you could trigger a script that calls your Maven job, initiating a new build, downloading the new code, and executing necessary tasks.

That's essentially what a Git hook does. It acts as a trigger when a specified event occurs.

In this case, we are going to focus on **PushEvents**, which occur whenever someone pushes to a specific branch.

**Creating a Git Hook in a Git Container**

To achieve this, we need to create the Git hook inside the Git container.

1. Run the following command to list running Docker containers:
   ```sh
   docker ps
   ```
2. Access the Git server container:
   ```sh
   docker exec -it <git-server-container> bash
   ```
3. Navigate to the repository directory:
   ```sh
   cd /var/opt/gitlab/git-data/repositories/<group>/<repository>
   ```
4. List the repository structure:
   ```sh
   ls
   ```
5. Create a new directory for custom hooks:
   ```sh
   mkdir custom_hooks && cd custom_hooks
   ```
6. Create the script that will be triggered when someone pushes to this repository.

**Writing the Git Hook Script**

Inside the `custom_hooks` directory, create a `post-receive` file and add the following content:

```sh
#!/bin/bash

if ! [ -t 0 ]; then
	read -a ref
fi

IFS='/' read -ra REF <<< "${ref[2]}"
branch="${REF[2]}"

if [ $branch == "master" ]; then
	crumb=$(curl -u "jenkins:1234" -s 'http://jenkins:8080/crumbIssuer/api/xml?xpath=concat(//crumbRequestField,":",//crumb)')
	curl -u "jenkins:1234" -H "$crumb" -X POST http://jenkins:8080/job/maven-job/build?delay=0sec

	if [ $? -eq 0 ]; then
		echo "*** Ok"
	else
		echo "*** Error"
	fi

fi
```
- This script checks if the push occurred on the **master** branch.
- If true, it generates an authentication crumb.
- Finally, it triggers the **Maven job** using Jenkins.
- Note: The Jenkins URL should be the internal service name from the `docker-compose` file.

**Saving and Applying Permissions**

1. Save the file and verify its content:
   ```sh
   cat post-receive
   ```
2. Make the script executable:
   ```sh
   chmod +x post-receive
   ```
3. Change the owner and group of the `custom_hooks` directory to `git`:
   ```sh
   chown -R git:git /var/opt/gitlab/git-data/repositories/<group>/<repository>/custom_hooks
   ```

Now, the Git hook is correctly set up. Whenever **you push to the master branch**, the script will execute, triggering the Maven job.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

### 6. Trigger your Jenkins job using a Git Hook

**1. Navigate to the Maven Folder**

Remember that this folder refers to our Git server. To verify this, run:
```sh
cat .git/config
```
This should display our Git repository configuration, including `gitlab.example.com`.

**2. Modify the Code to Trigger the Git Hook**

Let's search for the text "Hello" recursively in our files:
```sh
grep -r "Hello"
```
This will show that we have two files containing this text. We will modify `App.java` to update the application message:
```java
System.out.println("Hello World from Git and Jenkins");
```
Save the changes and proceed to modify the test file `AppTest.java`. Locate the line that uses `assertEquals` and update it as follows:
```java
assertEquals("Hello World from Git and Jenkins", someFunction());
```
Save the file.

**3. Commit and Push the Changes**

Check the modified files:
```sh
git status
```
You should see that `App.java` and `AppTest.java` have been modified. Now, commit and push the changes:
```sh
git add src
```
```sh
git commit -m "Test Git hook trigger"
```
```sh
git push origin master
```
After pushing, you will see the upload process and kernel command output.

**4. Verify the Jenkins Job Execution**

Go to your Jenkins project and reload the page. Check the last execution number (e.g., 18). Now, navigate to the Jenkins job console, where you should see:
- The Jenkins user triggering the build.
- The repository downloading the latest code.
- The build, test, and packaging process being executed.
- The updated message `Hello World from Git and Jenkins` appearing in the output.

This confirms that any changes pushed to the repository will trigger the Jenkins job automatically.

**5. Testing an Intentional Failure**

Modify the test file again to create an intentional failure. Run:
```sh
grep -r "Hello"
```
Modify `AppTest.java` to make the test fail by changing the assertion:
```java
assertEquals("Hello World from Git", someFunction());
```
Since `App.java` contains a different message, this test will fail. Save the file and run:
```sh
git status
```
```sh
git add src
```
```sh
git commit -m "Intentional failure"
```
```sh
git push origin master
```

**6. Analyzing the Failure in Jenkins**

After pushing the changes, check Jenkins again. Navigate to the console output, where you should see:
- The test execution failing due to assertion mismatch.
- The specific reason for the failure.

`This demonstrates` how Jenkins helps **identify issues early**. Whenever a faulty commit is pushed, the job will fail, and you will be able to analyze and fix the root cause before deployment.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

## Section 12: Jenkins & DSL
### 1. Install the DSL Plugin

1. **Access Plugin Management**
   - Navigate to **Manage Jenkins**.
   - Click on **Manage Plugins**.
   
2. **Locate the Job DSL Plugin**
   - Go to the **Available** tab.
   - Use the search bar and filter by the keyword `dsl`.
   - The **Job DSL** plugin should appear at the top of the list.
   
3. **Install the Plugin**
   - Select the **Job DSL** plugin.
   - Click on **Install without restart**.
   - Once the installation is complete, restart Jenkins by clicking **Restart Jenkins when installation is complete**.

![image](images/dsl_plugin_1.png)

4. **Verify the Installation**
   - Once Jenkins has restarted, navigate back to **Manage Jenkins** > **Manage Plugins**.
   - Go to the **Installed** tab.
   - Use the search bar and filter by `dsl`.
   - You should see the **Job DSL** plugin listed, confirming a successful installation.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

### 2. What is a Seed Job in DSL?

**Understanding the Seed Job**

A **Seed Job** is a special Jenkins job responsible **for creating other jobs**. It acts as a template or a **parent job** that defines the configuration and `structure for multiple jobs`.

**How It Works**

1. The seed job is created like any other `Jenkins job`.
2. Inside the **seed job**, you define the configuration `for multiple jobs`.
3. When the seed job runs, it generates and configures the specified jobs automatically.

**Steps to Create a Seed Job**

1. **Create a New Item**
   - Navigate to Jenkins and create a new item.
   - Name it something like `job-dsl` (or any preferred name).
   - Choose **Freestyle Project** and click **OK**.

2. **Configure the Build Step**
   - Scroll down to the **Build** section.
   - Add a new build step and select **Process Job DSL**.
   
3. **Define the DSL Script**
   - You have two options:
     - **Use the provided DSL script**: Manually define job configurations within Jenkins.
     - **Look on the file system**: Load a script from the Jenkins container file system.
   - Initially, you can define job configurations directly in Jenkins.

![images](images/seed_job_in_dsl_1.png)

4. **Execute the Seed Job**
   - When the seed job runs, it processes the defined DSL script.
   - The jobs described in the script are automatically created and configured.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

### 3. Understand the DSL Structure

**Executing the DSL Job**
1. Open the job that was previusly created `job_dsl`
2. Scroll down to the **Build** section.
3. Add a new build step and select **Process Job DSL**.
4. Paste this content.
```groovy 
// Creates a new job in Jenkins named 'job_dsl_created'
job('job_dsl_created') {

}
```
3. Save the configuration.
4. Build the project to execute the job.

![images](images/understand_the_dsl_structure.png)

5. Verify the execution log to confirm that `job_dsl` was successfully generated.

![image](images/understand_the_dsl_structure_1.png)

**Note**: It is now necessary to approve the script.

**Manually Approve the Script**
1. Go to **Jenkins** Dashboard.
2. Navigate to **Manage Jenkins** → **In-process Script Approval**
3. You’ll see a list of scripts waiting for approval.
4. **Approve the script manually** and then re-run the job.

**Verifying the Created Job**

1. Navigate to the **Jenkins Dashboard**.
2. Locate the newly created job in the list.

![image](images/understand_the_dsl_structure_2.png)

3. Click on the job to inspect its details.
4. Check the **parent job** (seed job), which should be `job_dsl`.

![image](images/understand_the_dsl_structure_3.png)

**Understanding DSL Documentation**

To explore more about DSL options:

[https://jenkinsci.github.io/job-dsl-plugin/#path/job](https://jenkinsci.github.io/job-dsl-plugin/#path/job)

![image](images/understand_the_dsl_structure_4.png)

**Reviewing the Job Configuration**

1. Open the created job and click **Configure**.
2. Notice that the job is **empty**, since we didn't define additional settings inside the curly braces `{}`.

![image](images/understand_the_dsl_structure_5.png )

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

### 4. Adding a Description to a Job in DSL

**Adding a Description Using DSL**

**Important Note**

`Manually modifying` a job created via DSL **is not recommended**, as Jenkins will mark it as manually changed. Instead, always **update jobs** `through` the **seed job**.

**Documentation**

[https://jenkinsci.github.io/job-dsl-plugin/#method/javaposse.jobdsl.dsl.jobs.FreeStyleJob.description](https://jenkinsci.github.io/job-dsl-plugin/#method/javaposse.jobdsl.dsl.jobs.FreeStyleJob.description)

![image](images/description_to_a_job_in_dsl_5.png )

**Steps to Add a Description**

1. Open the **seed job configuration**.
2. Navigate to the **DSL script**.
3. Create or modify a job definition.
4. Inside the curly braces `{}`, add the `description` function.
```groovy
job('job_dsl_example') {
    description('This is my awesome Job')
}
```

![image](images/description_to_a_job_in_dsl_1.png)

5. Save the **seed job**.
6. Run the **seed job** to apply changes.

**Note**: It is now necessary to approve the script.

**Manually Approve the Script**
1. Go to **Jenkins** Dashboard.
2. Navigate to **Manage Jenkins** → **In-process Script Approval**
3. You’ll see a list of scripts waiting for approval.
4. **Approve the script manually** and then re-run the job.

**Verifying the Description**

1. Navigate to the **Jenkins Dashboard**.
2. Locate the newly created job (`job_dsl_example`).
3. Click on the job.
4. The **Description** field should now be populated.
5. If you open the job configuration, you’ll also see the description set.

![image](images/description_to_a_job_in_dsl_2.png)
![image](images/description_to_a_job_in_dsl_3.png)
![image](images/description_to_a_job_in_dsl_4.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

### 5. Parameters

**Understanding Parameters in DSL**
You define parameters inside **curly braces `{}`**, specifying the type and attributes of each parameter.

**Types of Parameters**

1. **String Parameter**
   - Defines a text-based input.
   - Accepts a name, default value, and description.
   
2. **Boolean Parameter**
   - Defines a true/false toggle.
   - Accepts a name and a default value.
   
3. **Choice Parameter**
   - Defines a dropdown selection.
   - Accepts a name and a list of options.
   - Allows setting a default option.

**Documentation**

[FreeStyleJob parameters](https://jenkinsci.github.io/job-dsl-plugin/#method/javaposse.jobdsl.dsl.jobs.FreeStyleJob.parameters)

![image](images/parameters_job_dsl_1.png)

**Implementing the Parameters**

1. **Open the Seed Job**
   - Navigate to **Jenkins**.
   - Open the **seed job** configuration.
   
2. **Modify the DSL Script**
   - Add the **parameters** block with required values.
    ```groovy
    job('job_dsl_example') {
        description('This is my awesome Job')
      
        parameters {
            stringParam('Planet', defaultValue = 'world', description = 'This is the world')
      booleanParam('FLAG', true)
            choiceParam('OPTION', ['option 1 (default)', 'option 2', 'option 3'])
        }
    }
    ```
   - Save the configuration.
   
3. **Build the Seed Job**
   - Execute the **seed job**.
   - Verify that the job was successfully created.

**Note**: It is now necessary to approve the script.

**Manually Approve the Script**
1. Go to **Jenkins** Dashboard.
2. Navigate to **Manage Jenkins** → **In-process Script Approval**
3. You’ll see a list of scripts waiting for approval.
4. **Approve the script manually** and then re-run the job.

**Verifying the Parameters**

1. Navigate to **Jenkins Dashboard**.
2. Open the created job (`dsl_example`).
3. Click **Configure** and check the parameters:
   - **String Parameter**: `Planet` with default `World`.
   - **Boolean Parameter**: `FLAG` set to `true`.
   - **Choice Parameter**: `OPTION` with available choices.
4. Click **Build with Parameters** to test parameterized execution.

![image](images/parameters_job_dsl_1.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

## Section 13: CI/CD - Definitions
### 1. Introduction to CI/CD
CI/CD is a way to build, test, and deploy code automatically.

Before CI/CD, people did many tasks by hand, like testing and deploying code. This could cause mistakes and take a lot of time.

With CI/CD, you create a workflow that does everything for you.

- **CI (Continuous Integration):** build and test the code.
- **CD (Continuous Delivery / Deployment):** deploy the code to test environments and then to production.

CI/CD helps teams deploy faster and with fewer errors.

![image](images/continuous_integration.png)

### 2. Continuous Integration
First, your code is stored in a **Git repository**.  
Developers push their code (for example, Java code) to this repository.

When the code is pushed, the **CI process starts automatically**, usually using a tool like **Jenkins**.

The CI process does two main things:
- **Build the application** (for example, using Maven to create a package).
- **Test the application** to make sure it works correctly.

Testing is very important because it shows that the application behaves as expected.

In short, **Continuous Integration means building and testing your application automatically**.

### 3. Continuous Delivery
Continuous Delivery happens **after Continuous Integration** finishes successfully.  
This means the application is built and all tests pass.

Next, the application is **deployed to a test environment**, like:
- Dev
- QA
- Staging

This step is **optional**. You may use it or not.

In the test environment, you run more tests, usually **acceptance tests**, to check if the application works well before production.

Remember:
- **Continuous Integration:** build and test the application.
- **Continuous Delivery:** deploy to a test environment and test again.

### 4. Continuous Deployment
Continuous Deployment is the **final step** in CI/CD.

After:
- the application is built,
- tested many times,
- deployed to a test environment,
- tested again,

then the application is **deployed to production** automatically.

The way to deploy depends on the application and where it is hosted.

Continuous Integration and Continuous Deployment are strategies to:
- automate code delivery,
- reduce human work,
- reduce errors.

In short, **Continuous Deployment means automatically deploying your application to production**.

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

## Section 14: Jenkins Pipeline - Jenkinsfile
### 1. Introduction to Pipeline
![Diagrama de pipeline](https://www.jenkins.io/doc/book/resources/pipeline/realworld-pipeline-flow.png)
https://www.jenkins.io/doc/book/pipeline/

A pipeline is the **full workflow** used in the CI/CD process.  
It starts when developers write and push code and ends when the application is deployed to production.

A pipeline has **many stages**.  
Each stage is one step in the workflow.

A common pipeline looks like this:
- **Code push** to Git (this starts the pipeline).
- **Checkout code** (download the new code).
- **Build the application** (for example, using Maven).
- **Create a Docker image**.
- **Test the application**.
- **Deploy to production**.

You can add as many stages as you need.

In short, a **pipeline is a sequence of steps that automatically build, test, and deploy your application**.

### 2. Introduction to Jenkinsfile

- A pipeline is a set of **stages**.
- Each **stage** is one step in the workflow.
- Example stages:
  - **Build**
  - **Test**
  - **Deploy**

https://www.jenkins.io/doc/book/pipeline/jenkinsfile/

**Types of Jenkins Pipelines**
There are **two types** of pipelines in Jenkins:

1. **Declarative Pipeline**
   - Very **simple and easy to use**
   - Good for **SysAdmins** or people with little coding experience
   - Uses a **template structure**
   - You can run Bash, Python, Ansible, or other tools inside stages

```jenkinsfile
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
```

2. **Scripted Pipeline**
   - More **complex**
   - Written in **Groovy** (similar to Java)
   - Requires programming knowledge
   - Harder if you don’t know Java or Groovy

```jenkinsfile
node {
    checkout scm
    /* .. snip .. */
}
```

### 3. Install the Jenkins Pipeline Plugin
![image](images/install_the_jenkins_pipeline_plugin.png)
- Go to **Manage Jenkins → Manage Plugins**.
- Search for **Pipeline** in the *Installed* or *Available* tab.
- Pipeline is usually **installed by default** with suggested plugins.
- If not installed, you can **install it manually**.
- Make sure the **Pipeline plugin is installed**, because it is very important.

### 4. Create your first Pipeline
- A pipeline file starts with **pipeline** and needs **agent any**.
- The main part is **stages**.
- Each stage has **steps** where commands are executed.

Example Stages
```jenkinsfile
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
```
- **Build** → echo "Building"
- **Test** → echo "Test"
- **Deploy** → echo "Deploying"

- Steps can run **scripts, shell commands, and deployments**.
- Create a **new Pipeline project** in Jenkins.
- Paste the pipeline script and **build the project**.
- Jenkins shows each stage and its **logs in Console Output**.

- You have now created your **first Jenkins pipeline**.

### 5. Add multi-steps to your Pipeline
In this section, you learn how to run real commands in a Jenkins pipeline using `sh`.
The instructor shows how to create one stage called `build` and inside it execute commands like `echo` and `ls`. You can run one command in a single line or multiple commands using triple quotes so you can write several lines. After saving and running the pipeline, you can see the results of each command in the Jenkins console output, which shows the printed messages and the result of the Linux command.

1. **Open your Jenkins project**  
   - Go to the pipeline you want to configure.

2. **Set up a stage**  
   - Create a stage called `build` (or use the existing one).

3. **Add commands with `sh`**  
   - For one command:
     ```groovy
     sh 'echo "My first pipeline"'
     ```
   - For multiple commands:
     ```groovy
     sh '''
     echo "My first pipeline"
     echo "I can do more stuff here"
     ls
     '''
     ```
   - Example:
```groovy
   pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "My first pipeline"'
                sh '''
                    echo "By the way, I can do more stuff in here"
                    ls -lah
                '''
            }
        }
    }
  }
```
   
4. **Save the changes**  
   - Save the pipeline configuration.

5. **Run the pipeline**  
   - Click **Build Now** to start it.

6. **Check the output**  
   - Go to **Console Output** to see:
     - Messages from `echo`
     - Results from Linux commands (`ls`, etc.)

7. **Notes**  
   - You can run many commands in one stage.  
   - Use triple quotes `'''` for multiple lines.  
   - Everything runs and shows in the Jenkins console.

### 6. Retry

- **Retry** means trying a command again if it fails.  
- Example: a stage `Timeout` has a command `sh "I"` (invalid, will fail).  
- Using `retry(3)` makes Jenkins try the command **up to 3 times** before failing.  
- After running, the **console shows all attempts and errors**.  
- Useful when a command may fail sometimes but should be retried automatically.  
- Now you know how to **retry commands in a pipeline**.

**Example**
```groovy
pipeline {
    agent any
    stages {
        stage('Timeout') {
            steps {
                retry(3) {
                    sh 'I am not going to work :c'
                }
            }
        }
    }
}
```
### 7. Timeouts
![Image](images/timeout.png)
- **Timeout** stops a task if it takes too long.  
- Example: a stage has a command `sleep 5` (waits 5 seconds).  
- We set a timeout of **3 seconds**, so Jenkins stops the task automatically.  
- Commands that finish quickly (like `echo hello`) are not affected.  
- Useful to prevent tasks from **getting stuck** or taking longer than expected.  
- Now you know how to use the **timeout instruction** in a Jenkins pipeline.
**Example**
```groovy
pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                retry(3) {
                    sh 'echo hello'
                }

                timeout(time: 3, unit: 'SECONDS') {
                    sh 'sleep 5'
                }
            }
        }
    }
}
```
### 8. Environment variables

- **Purpose:** Store values that can be used anywhere in your pipeline.
  Example:
```groovy
pipeline {
    agent any

    environment {
        NAME = 'ricardo'
        LASTNAME = 'gonzalez'
    }

    stages {
        stage('Build') {
            steps {
                sh 'echo $NAME $LASTNAME'
            }
        }
    }
}
```

- **How to define:**  
  Use the `environment` block with curly braces `{}`.  
  Example:
  ```groovy
  environment {
      NAME = "Ricardo"
      LAST_NAME = "Gonzalez"
  }
  ```

- **How to use:**  
  Reference variables with a dollar sign `$`, for example:
  ```groovy
  echo $NAME $LAST_NAME
  ```

- **Steps to apply:**
  1. Copy the pipeline code with `environment` block.
  2. Go to your job configuration in Jenkins.
  3. Delete old pipeline code and paste the new one.
  4. Save and run the pipeline.
  5. Check **Console Output** to see variables in action (`echo Ricardo Gonzalez`).

- **Notes:**  
  - Variables can store names, credentials, or any values needed in the pipeline.  
  - Commands using these variables work normally.  
  - Now you know how to **create and use environment variables** in Jenkins pipelines.

### 9. Credentials
- **Purpose:** Safely use sensitive information in your pipeline.
**Example**
```groovy
pipeline {
    agent any

    environment {
        secret = credentials('TEST')
    }
    stages {
        stage('Example stage 1') {
            steps {
                sh 'echo $secret'
            }
        }
    }
}
```
- **How to define:**
Use an `environment` block with `credentials` function:
```groovy
environment {
SECRET_VAR = credentials('SECRET_TEXT')
}
```

- **Steps to apply:**
1. Go to Jenkins -> Manage -> Credentials -> Global.
2. Create a new credential (e.g., Secret Text `1,2,3,4`) with an **ID** (e.g., `SECRET_TEXT`).
3. Copy pipeline code with `environment { SECRET_VAR = credentials('SECRET_TEXT') }`.
4. Go to your pipeline job -> Configure.
5. Delete old code and paste new pipeline code.
6. Save and build the pipeline.
![Image](images/environment_variables_1.png)
![Image](images/environment_variables_2.png)
![Image](images/environment_variables_3.png)

- **Notes:**
- Jenkins will **not display the secret value** in console output.
- The **ID** of the credential is important to reference it correctly.
- Useful for storing passwords, tokens, or other sensitive information.
- Now you know how to **use credentials securely** in Jenkins pipelines.

### 10. Post actions
- Post actions run **after** the pipeline ends.
- They are inside the **post** section.

**Types**
- **always**: runs every time  
- **success**: runs if the job succeeds  
- **failure**: runs if the job fails  

You can use one or more post actions.

**Summary**  
Post actions define what Jenkins does after a job finishes.

**Examples**  
**Case 1: Failure**  
This pipeline fails because of `exit 1`.
```groovy
pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'echo "Fail!"; exit 1'
            }
        }
    }
    post {
        always {
            echo 'I will always get executed :D'
        }
        success {
            echo 'I will only get executed if this success'
        }
        failure {
            echo 'I will only get executed if this fails'
        }
        unstable {
            echo 'I will only get executed if this is unstable'
        }
    }
}
```
![Image](images/post_actions_1.png)

**Case 2: Success**  
This pipeline succeeds (no error).
```groovy
pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh 'echo I am good'
            }
        }
    }
    post {
        always {
            echo 'I will always get executed :D'
        }
        success {
            echo 'I will only get executed if this success'
        }
        failure {
            echo 'I will only get executed if this fails'
        }
        unstable {
            echo 'I will only get executed if this is unstable'
        }
    }
}
```
![Image](images/post_actions_2.png)

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---

## Section 15: CI/CD + Jenkins Pipeline + Docker +  Maven
### 1. Introduction
![Image](images/section_15_1.png)
- In this section, we will build a **real CI/CD pipeline**.
- We will use **Jenkinsfile**, **Jenkins**, **Docker**, and **Maven**.
- Jenkins will **build a Docker image**.
- Jenkins will **test the Docker image**.
- If the tests pass, Jenkins will **push the image to a registry**.
- After that, the image will be **deployed to production**.
- We will work with a **Maven application**.
- You will learn **all the steps** needed to complete this process.

### 2. Notes on Docker in Docker
- Docker-in-Docker (**DinD**) is good for learning but not for production.
- Use **Kubernetes agents** or **external clusters** for real projects.
- Allows **build and run Docker containers locally**.

**Docker Installation**  
- Install Docker as **root** using official docs.
- Adds **GPG key** and **repository**.
- Installs **docker-ce** and **docker-compose**.
- Switch back to **jenkins user**. 

```dockerfile
# FROM jenkins/jenkins
##############################################
# The updated Ansible installation goes here #
##############################################
 
# Docker installation starts here
 
USER root
 
# Add Docker's official GPG key:
RUN apt-get update && apt-get install ca-certificates curl && \
    install -m 0755 -d /etc/apt/keyrings && \
    curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc && \
    chmod a+r /etc/apt/keyrings/docker.asc
 
# Add the repository to Apt sources:
RUN echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  tee /etc/apt/sources.list.d/docker.list > /dev/null
 
RUN apt-get update && apt-get install docker-ce docker-compose-plugin -y
 
USER jenkins
```
💡 Note: Don't forget to include the updated Ansible installation

### 3. Learn how to install Docker inside of a Docker Container
1. Start all containers using `docker-compose start`.
2. Stop the Git server because it uses many resources.
3. Enter the Jenkins container.
4. Check that Docker is not installed inside Jenkins.
   ![Image](images/section_15_2.png)
5. Explain why Docker is needed inside Jenkins:
   - Jenkins will build Docker images and run Docker commands.
6. Create a new **Dockerfile** inside the pipeline directory.
7. Use a Debian-based Dockerfile because Jenkins runs on Debian.
8. Install required packages, then install **Docker** and **docker-compose**.
9.  Add the Jenkins user to the Docker group.
10. Switch back to the Jenkins user after installation.
11. Update the **docker-compose.yml** file:
    - Use the new Docker image.
    - Set the build context to the pipeline directory.
12. Mount `/var/run/docker.sock` into the Jenkins container.
13. Build the new image using `docker-compose build`.
14. Recreate the Jenkins container using `docker-compose up -d`.
15. Enter the Jenkins container again.
16. Try running `docker ps` and see a permission error.
17. Fix permissions by changing the owner of `docker.sock` to Jenkins user (UID 1000).
18. Enter the Jenkins container again.
19. Run `docker ps` successfully.
20. Jenkins can now run Docker commands and see host containers.
21. Docker inside Docker is working and ready to build images.

```dockerfile
FROM jenkins/jenkins
USER root

RUN apt-get update && apt-get install python3-pip -y

# New lines to set up a virtual environment
####
ENV ANSIBLE_VENV=/ansible_venv
RUN mkdir $ANSIBLE_VENV && \
    chown jenkins:jenkins $ANSIBLE_VENV && \
    apt-get install python3-venv -y
####

USER jenkins

# Activate the virtual environment
RUN python3 -m venv $ANSIBLE_VENV

# Use the venv to install Ansible
RUN $ANSIBLE_VENV/bin/pip3 install ansible

# Ensure the Ansible binary is accessible
ENV PATH=$PATH:$ANSIBLE_VENV/bin

##################
# Install Docker #
##################
USER root

# Add Docker's official GPG key:
RUN apt-get update && apt-get install ca-certificates curl && \
    install -m 0755 -d /etc/apt/keyrings && \
    curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc && \
    chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
RUN echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  tee /etc/apt/sources.list.d/docker.list > /dev/null

RUN apt-get update && apt-get install docker-ce docker-compose-plugin -y

USER jenkins
```

### 4. Define the steps for your Pipeline
1. Use a basic pipeline file as a skeleton.
2. The pipeline has four stages:
   - Build
   - Test
   - Push
   - Deploy
3. For now, each stage only uses simple `echo` commands.
4. The real work will be done using bash or shell scripts.
5. Each stage will call a script to execute tasks.
6. This keeps the Jenkinsfile simple and clean.
7. Copy the pipeline content.
8. Go to the terminal.
9. Navigate to the pipeline directory.
10. Create a **Jenkinsfile** at the same level as the Dockerfile.
11. Paste the pipeline content into the Jenkinsfile.
12. Save the file.
13. Now the directory contains:
    - Dockerfile
    - Jenkinsfile
14. These files will be used later in the project.

```groovy
pipeline {

    agent any

    stages {

        stage('Build') {
            steps {
                sh '''
                    echo build
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'echo test'
            }
        }

        stage('Push') {
            steps {
                sh 'echo push'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo deploy'
            }
        }
    }
}
``` 
### 5. Notes on building a jar with docker
**Ensure Maven Version Consistency**

1. Always use the latest stable version of Maven.
2. Use the same Maven version as in the Jenkins & Maven section.
3. Example:
   - If Jenkins uses Maven **3.9.9**, use the Docker image `maven:3.9.9`.
4. This avoids compatibility and version issues.

**Optional: Fix Memory Errors**

1. You may see this error:
   - `library initialization failed - unable to allocate file descriptor table - out of memory`
2. Fix it by adding this flag to the Docker run command:
   ```bash
   --ulimit nofile=65536:65536
This increases the file descriptor limit, preventing system resource allocation issues.

### 6. Build: Create a Jar for your Maven App using Docker
1. Go to the Jenkins working directory.
2. Enter the `pipeline` folder.
3. Verify that `Dockerfile` and `Jenkinsfile` exist.
4. Go one level back and locate the Java Maven application downloaded from Git.
5. Copy the Java project into the `pipeline` folder.
6. Name the new folder `java-app`.
7. Enter the `java-app` folder and verify all project files exist.
8. Remove the `.git` directory to avoid future Git conflicts.
9. Go back to the pipeline root level.
10. Create a `jenkins` folder to store Jenkins-related files.
11. Inside `jenkins`, create a `build` subfolder for build scripts.

**Use Maven with Docker**

12. Choose a Maven Docker image (example: `maven:3-alpine`).
13. Pull the Maven image using `docker pull`.
14. Verify the image exists using `docker images`.

**Build the JAR Manually (Interactive)**

15. Run a Maven container with:
    - The project folder mounted to `/app`
    - Interactive mode enabled
16. Enter `/app` inside the container.
17. Run `mvn package` to build the project.
18. Maven downloads dependencies and builds the JAR.

**Persist Maven Dependencies**

19. Maven stores dependencies in `/root/.m2`.
20. Mount `/root/.m2` as a volume to persist downloads.
21. Exit the container and confirm dependencies remain on the host.

**Automate the Build (Non-Interactive)**

22. Use Docker with:
    - Mounted project folder (`/app`)
    - Working directory set to `/app`
    - No interactive shell
23. Run Maven automatically using:
    - `mvn -B -DskipTests clean package`
24. Docker builds the JAR without entering the container manually.
25. Dependencies are reused from `/root/.m2`.

**Verify the Result**

26. Check `java-app/target/` on the host.
27. Confirm the JAR file was created.
28. Delete the JAR and run the command again.
29. The JAR is rebuilt without re-downloading dependencies.

**Result**

30. You can now build a Java JAR using Docker and Maven.
31. The process is fast, repeatable, and ready for Jenkins pipelines.
    
### 7. Build: Write a bash script to automate the Jar creation
**Build the JAR Using a Jenkins Bash Script**
```groovy
#!/bin/bash

echo "***************************"
echo "** Building jar ***********"
echo "***************************"

WORKSPACE=/home/jenkins/jenkins-data/jenkins_home/workspace/pipeline-docker-maven

docker run --rm  -v  $WORKSPACE/java-app:/app -v /root/.m2/:/root/.m2/ -w /app maven:3.9.9 "$@"
```

1. Go to the same level as the Java application.
2. Execute the build script using the full path:
   - `jenkins/build`
3. If no parameters are passed, the script may fail.
4. Pass the required parameters to build the JAR.
5. Run the script again with parameters.
6. The script builds a new JAR successfully.
7. The JAR is saved inside:
   - `java-app/target`
8. Using a Bash script is easier than writing long Docker commands.
9. Bash scripts help automate the build process.
10. You only need to run the script and pass parameters.

**Test the Script**

11. Verify the JAR exists in `java-app/target`.
12. Delete the existing JAR file.
13. Confirm the JAR is removed.
14. Execute the build script again.
15. Check `java-app/target` folder.
16. The JAR is created again.

**Result**

17. The build process runs correctly using the script.
18. You have automated the JAR build using a simple Bash script.
19. This approach is ready to be used in Jenkins pipelines.

### 8. Notes on creating the Dockerfile

1. In the next step, a Dockerfile will be created.
2. Do NOT use `openjdk` because it is deprecated.
3. Use a supported Java image instead.

**Recommended Java Images**

4. Available alternatives include:
   - `amazoncorretto`
   - `eclipse-temurin`
   - `ibm-semeru-runtimes`
   - `ibmjava`
   - `sapmachine`
5. In this course, **amazoncorretto** is used.

**Match Java and Maven Versions**

6. The Java version must match the Maven build version.
7. Check the Java version used by Maven with:
   ```bash
   docker run --rm maven:3.9.9 mvn -version | grep Java
   ```
**Example output:**

Java version: 21.0.6, vendor: Eclipse Adoptium, runtime: /opt/java/openjdk
From this, you can see that the correct Docker image to use would be:
amazoncorretto:21.0.6 🎯.

That's what you will use in your FROM instruction.

### 9. Build: Create a Dockerfile and build an image with your Jar
1. The goal is to create a Docker image using the JAR built by Maven.
2. A Docker image with Java installed is required.
3. Search for a Java Docker image.
4. Choose `openjdk:8-jre-alpine` for this exercise.
   - It includes Java.
   - It is small and lightweight (Alpine).

**Create the Dockerfile**

5. Go to the Jenkins directory.
6. Enter the `build` folder.
7. Create a new file called `Dockerfile-Java`.
8. Start the Dockerfile with:
   - `FROM openjdk:8-jre-alpine`
9. Create a directory `/app` inside the container.
10. Copy the JAR file from the host into the container:
    - Copy `*.jar` to `/app/app.jar`
11. Define the command to run the JAR:
    - Use `java -jar /app/app.jar`

**Prepare the JAR File**

12. The JAR file must exist in the same directory as the Dockerfile.
13. Copy the JAR from:
    - `java-app/target`
14. Paste it into the `build` directory.

**Build the Docker Image**

15. Run the Docker build command.
16. Specify the Dockerfile and image tag (example: `test`).
17. Use `.` as the build context.
18. Docker downloads the base image if needed.
19. The image is built successfully.

**Verify the Image**

20. List Docker images and confirm the image exists.
21. Run a temporary container with an interactive shell.
22. Go to `/app` inside the container.
23. Confirm the JAR file is present.

**Run the Application**

24. Exit the container.
25. Run the image in detached mode.
26. The container executes the JAR automatically.
27. Check container logs.
28. Confirm the output (example: `hello world`).

## Result

29. The Java application is successfully dockerized.
30. The Docker image contains the JAR and runs it automatically.

### 10. Build: Create a Docker Compose file to automate the Image build process
### 11. Build: Write a bash script to automate the Docker Image creation process
### 12. Build: Add your scripts to the Jenkinsfile
### 13. Test: Learn how to test your code using Maven and Docker
### 14. Test: Create a bash script to automate the test process
### 15. Test: Add your test script to Jenkinsfile
### 16. Create a remote machine to deploy your containerized app
### 17. Push: Create your own Docker Hub account
### 18. Push: Create a Repository in Docker Hub
### 19. Push: Learn how to Push/Pull Docker images to your Repository
### 20. Push: Write a bash script to automate the push process
### 21. Push: Add your push script to Jenkinsfile
### 22. Deploy: Transfer some variables to the remote machine
### 23. Deploy: Deploy your application on the remote machine manually
### 24. Deploy: Transfer the deployment script to the remote machine
### 25. Deploy: Execute the deploy script in the remote machine
### 26. Deploy: Add your deploy script to Jenkinsfile
### 27. Create a Git Repository to store your scripts and the code for the app
### 28. Create the Jenkins Pipeline. Finally!
### 29. Modify the path when mounting Docker volumes
### 30. Create the Registry Password in Jenkins
### 31. Add the private ssh key to the Jenkins container
### 32. Add post actions to Jenkinsfile
### 33. Execute your Pipeline manually
### 34. Notes on Git Hooks
### 35. Create a Git Hook to automatically trigger your Pipeline
### 36. Start the CI/CD process by committing new code to Git!

<div align="right">
  <strong>
    <a href="#table-of-contents" style="text-decoration: none;">↥ Back to top</a>
  </strong>
</div>

---
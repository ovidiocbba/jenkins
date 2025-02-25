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

# 5. Create a role to execute jobs, and assign that role to your user

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

# 6. Learn how to restrict Jobs to users using Project Roles

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

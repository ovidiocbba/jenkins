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

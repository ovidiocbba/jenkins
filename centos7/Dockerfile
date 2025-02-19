# Use CentOS 7 as the base image
FROM centos:7

# Install the OpenSSH server
RUN yum -y install openssh-server

# Create a new user 'remote_user' with password '1234' (not secure for production)
RUN useradd remote_user && \
    echo "1234" | passwd remote_user --stdin && \  # Set the user's password
    mkdir /home/remote_user/.ssh && \  # Create the SSH directory for the user
    chmod 700 /home/remote_user/.ssh  # Set proper permissions to secure the SSH directory

# Copy the public key to the authorized_keys file for passwordless SSH access
COPY id_rsa_remote.pub /home/remote_user/.ssh/authorized_keys

# Change ownership of the home directory and set correct permissions for the key
RUN chown remote_user:remote_user -R /home/remote_user && \  # Give ownership to the user
    chmod 400 /home/remote_user/.ssh/authorized_keys  # Secure the authorized_keys file

# Generate necessary SSH host keys
RUN ssh-keygen -A

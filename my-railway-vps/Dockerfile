# Use Ubuntu as the base image
FROM ubuntu:22.04

# Avoid prompts during package install
ENV DEBIAN_FRONTEND=noninteractive
ENV LANG=en_US.UTF-8
ENV LANGUAGE=en_US:en
ENV LC_ALL=en_US.UTF-8

# Install necessary packages
RUN apt-get update && \
    apt-get install -y locales curl wget unzip openssh-server && \
    locale-gen en_US.UTF-8 && \
    echo "root:railway" | chpasswd && \
    mkdir /var/run/sshd

# Expose the SSH port
EXPOSE 22

# Start SSH server
CMD ["/usr/sbin/sshd", "-D"]

FROM jenkins/jenkins:lts

USER root

# Install dependencies
RUN apt-get update && apt-get install -y curl unzip

# Download and install Docker CLI manually
RUN curl -fsSL https://download.docker.com/linux/static/stable/x86_64/docker-24.0.7.tgz -o docker.tgz \
    && tar -xvzf docker.tgz \
    && mv docker/docker /usr/local/bin/ \
    && rm -rf docker docker.tgz

# Create docker group and add jenkins user to it
RUN groupadd docker && usermod -aG docker jenkins

USER jenkins


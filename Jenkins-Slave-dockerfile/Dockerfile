FROM ubuntu:18.04

USER root

RUN mkdir -p /var/jenkins_home /home/jenkins
RUN groupadd jenkins \
    && useradd -g jenkins jenkins

RUN chown -R jenkins:jenkins /var/jenkins_home \
    && chown -R jenkins:jenkins /home/jenkins

WORKDIR /home/jenkins

RUN apt-get update && apt-get dist-upgrade -y && rm -rf /var/lib/apt/lists/*
RUN apt-get update && apt-get install -y \
    git \
    apt-transport-https \
    curl \
    init \
    openssh-server openssh-client \
    docker.io \
    vim \
 && rm -rf /var/lib/apt/lists/*

RUN service ssh start

# Install Java
RUN apt-get update && apt-get install -y openjdk-11-jdk && rm -rf /var/lib/apt/lists/*

# Install Maven
RUN apt-get update && apt-get install -y maven


EXPOSE 22

ENTRYPOINT ["tail"]
CMD ["-f","/dev/null"]

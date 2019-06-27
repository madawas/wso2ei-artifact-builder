FROM ubuntu:latest

MAINTAINER Madawa Soysa <madawa.soysa@gmail.com>

ARG JAVA_VERSION=8
ARG MAVEN_VERSION=3.6.1
ARG JMETER_VERSION=5.1.1

# Install OpenJDK-8
RUN apt-get update && \
    apt-get install -y openjdk-${JAVA_VERSION}-jdk

# Fix certificate issues
RUN apt-get update && \
    apt-get install ca-certificates-java && \
    update-ca-certificates -f;

ENV JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64

# Install Maven
RUN apt-get install -y curl && \
    curl -fsSL https://archive.apache.org/dist/maven/maven-3/${MAVEN_VERSION}/binaries/apache-maven-${MAVEN_VERSION}-bin.tar.gz | tar xzf - -C /usr/share \
    && mv /usr/share/apache-maven-${MAVEN_VERSION} /usr/share/maven \
    && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn

# Install Ansible
RUN apt-get install -y software-properties-common && \
    apt-add-repository --yes --update ppa:ansible/ansible && \
    apt-get install -y ansible

# Install Git
RUN apt-get -y install git

# Install Nodejs, NPM and postman
RUN curl -sL https://deb.nodesource.com/setup_8.x | bash - && \
    apt-get install -y apt-utils && \
    apt-get install -y nodejs && \
    npm install -g newman

# Install Jmeter
RUN apt-get install -y wget && \
    wget https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-${JMETER_VERSION}.tgz && \
    tar -xvzf apache-jmeter-${JMETER_VERSION}.tgz -C /opt/

RUN apt-get clean

ENV JMETER_HOME=/opt/apache-jmeter-${JMETER_VERSION}
ENV PATH=$JMETER_HOME/bin:$PATH

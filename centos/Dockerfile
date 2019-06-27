FROM centos:centos7

MAINTAINER Madawa Soysa <madawa.rc@gmail.com>

ARG JAVA_VERSON=1.8.0
ARG MAVEN_VERSION=3.6.1
ARG JMETER_VERSION=5.1.1

# Install ansible
RUN yum install -y java-${JAVA_VERSON}-openjdk-devel

ENV JAVA_HOME=/usr/lib/jvm/java

# Install Maven
RUN curl -fsSL https://archive.apache.org/dist/maven/maven-3/${MAVEN_VERSION}/binaries/apache-maven-${MAVEN_VERSION}-bin.tar.gz | tar xzf - -C /usr/share \
    && mv /usr/share/apache-maven-${MAVEN_VERSION} /usr/share/maven \
    && ln -s /usr/share/maven/bin/mvn /usr/bin/mvn

# Install Ansible and Git
RUN yum -y install epel-release && \
    yum -y install ansible && \
    yum -y install git

# Install Jmeter
RUN yum -y install wget && \
    wget https://archive.apache.org/dist/jmeter/binaries/apache-jmeter-${JMETER_VERSION}.tgz && \
    tar -xvzf apache-jmeter-${JMETER_VERSION}.tgz -C /opt/ && \
    yum clean all

ENV JMETER_HOME=/opt/apache-jmeter-${JMETER_VERSION}
ENV PATH=$JMETER_HOME/bin:$PATH
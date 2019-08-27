# Docker Container for Building and Deploying WSO2 Enterprise Integrator Artifacts

WSO2 Enterprise Integrator (WSO2 EI) is a comprehensive integration solution that enables communication among various, disparate applications. WSO2 EI provides a tooling package which allows developers to develop integration solutions and deploy to the server. This container is useful for creating a CI/CD pipeline for build/test and deploy WSO2 EI artifacts. (E.g. Create CI/CD Pipeline with Travis/GitLab CI)


## Available Tags
- [centos7-jdk8-mvn3.6-jmeter5.1, centos_latest, latest](https://github.com/madawas/wso2ei-artifact-builder/blob/master/centos/Dockerfile)

  Image is built on CentOS 7 and following software versions are installed in the container.
    - OpenJDK 8
    - Apache Maven: 3.6.1
    - Apache JMeter: 5.1.1
    - Ansible: latest
    - Newman: latest

- [ubuntu18.04-jdk8-mvn3.6-jmeter5.1, ubuntu_latest](https://github.com/madawas/wso2ei-artifact-builder/blob/master/ubuntu/Dockerfile)

  Image is built on Ubuntu 18.04 and following software versions are installed in the container.
    - OpenJDK 8
    - Apache Maven: 3.6.1
    - Apache JMeter: 5.1.1
    - Ansible: latest
    - Newman: latest

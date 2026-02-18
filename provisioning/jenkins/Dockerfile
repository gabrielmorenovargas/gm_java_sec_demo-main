FROM jenkins/jenkins:lts

USER root

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
      ca-certificates curl wget gnupg unzip \
 && rm -rf /var/lib/apt/lists/*

RUN cd /opt/ \
 && wget https://corretto.aws/downloads/latest/amazon-corretto-11-x64-linux-jdk.tar.gz -O amazon-corretto-11-x64-linux-jdk.tar.gz \
 && tar -xzf amazon-corretto-11-x64-linux-jdk.tar.gz \
 && rm -rf amazon-corretto-11-x64-linux-jdk.tar.gz \
 && wget https://archive.apache.org/dist/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz -O apache-maven-3.6.3-bin.tar.gz \
 && tar -xzf apache-maven-3.6.3-bin.tar.gz \
 && rm -rf apache-maven-3.6.3-bin.tar.gz \
 && chown -R jenkins:jenkins amazon-corretto-11.0.30.7.1-linux-x64 \
 && chown -R jenkins:jenkins apache-maven-3.6.3

USER jenkins

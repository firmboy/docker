FROM centos:latest

RUN yum -y install wget vim net-tools.x86_64

RUN mkdir /home/java \
    && mkdir /home/maven

COPY ./jdk-8u221-linux-x64.tar.gz /home/java
COPY ./apache-maven-3.6.3-bin.tar.gz /home/maven
WORKDIR /home/java

RUN tar xzf jdk-8u221-linux-x64.tar.gz -C /usr/local

WORKDIR /home/maven

RUN tar xzf apache-maven-3.6.3-bin.tar.gz -C /usr/local

ENV JAVA_HOME /usr/local/jdk1.8.0_221
ENV PATH $JAVA_HOME/bin:$PATH

ENV MAVEN_HOME /usr/local/apache-maven-3.6.3
ENV PATH $MAVEN_HOME/bin:$PATH

RUN rm -rf /usr/local/apache-maven-3.6.3/conf/settings.xml
COPY ./settings.xml /usr/local/apache-maven-3.6.3/conf

WORKDIR /root



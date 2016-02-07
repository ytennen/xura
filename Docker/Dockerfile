FROM centos:latest
MAINTAINER dima

RUN yum -y install mc
RUN yum -y install tomcat
RUN yum -y install java-1.8.0-openjdk-devel.x86_64
ENV NAME dima
RUN mkdir -p /logs
COPY {{WARFILE}} /usr/share/tomcat/webapps/petclinic.war

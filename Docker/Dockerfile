FROM centos:latest
MAINTAINER dima

RUN yum -y install mc
RUN yum -y install tomcat
RUN yum -y install java-1.8.0-openjdk-devel.x86_64
ENV NAME dima
RUN mkdir -p /logs
COPY remotecontent?filepath=org%2Fapache%2Faxis2%2Faxis2-webapp%2F1.7.0%2Faxis2-webapp-1.7.0.war /usr/share/tomcat/webapps/axis2-webapp-1.7.0.war
COPY spring-petclinic-YoniDima-1.0.0-20160207.111424-1.war /usr/share/tomcat/webapps/petclinic.war
RUN yum -y install systemd; yum clean all
VOLUME [ “/sys/fs/cgroup” ]
RUN echo -e "#!/bin/bash\ntomcat start\n" >/etc/init.d/tomcat
RUN chmod +x /etc/init.d/tomcat
RUN chkconfig tomcat on
RUN systemctl enable tomcat
CMD [“/usr/sbin/init”]

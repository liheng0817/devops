FROM centos:7
LABEL LIHENG007 liheng

RUN yum install -y java-1.8.0-openjdk maven curl git libtool-ltdl-devel && \
    yum clean all && \
    rm -fr /var/cache/yum/* && \
    mkdir -p /usr/share/jenkins

COPY slave.jar /usr/share/jenkins/slave.jar
COPY jenkins-slave /usr/bin/jenkins-slave
COPY settings.xml /etc/maven/settings.xml
RUN chmod +x /usr/bin/jenkins-slave
COPY kubectl /usr/bin/

ENTRYPOINT ["jenkins-slave"]

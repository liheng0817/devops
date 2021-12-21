FROM centos:7
LABEL LIHENG007 liheng
EXPOSE 8080
WORKDIR /opt

COPY jdk-8u151-linux-x64.tar.gz /opt
RUN tar zxf /opt/jdk-8u151-linux-x64.tar.gz -C /usr/local/ && rm -fr /opt/jdk-8u151-linux-x64.tar.gz
RUN ln -s /usr/local/jdk1.8.0_151 /usr/local/jdk

ENV JAVA_HOME /usr/local/jdk
ENV CLASSPATH=.:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin

COPY apache-tomcat-8.5.73.tar.gz /opt
RUN tar xf apache-tomcat-8.5.73.tar.gz -C /usr/local && rm -fr /opt/apache-tomcat-8.5.73.tar.gz
RUN mv /usr/local/apache-tomcat-8.5.73 /usr/local/tomcat

ENTRYPOINT /usr/local/tomcat/bin/startup.sh && tail -f /usr/local/tomcat/logs/catalina.out 

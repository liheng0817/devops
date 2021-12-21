FROM harbor.sly.com/library/tomcat8:latest
LABEL LIHENG007 liheng
RUN rm -rf /usr/local/tomcat/webapps/*
ADD target/*.war /usr/local/tomcat/webapps/ROOT.war 

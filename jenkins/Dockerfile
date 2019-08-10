FROM ubuntu:latest

RUN apt-get update -y && \
    apt-get install openjdk-8-jre -y && \
    echo "JAVA_HOME=/usr/" >> ~/.bashrc

ADD http://apache-mirror.rbc.ru/pub/apache/tomcat/tomcat-8/v8.5.43/bin/apache-tomcat-8.5.43.tar.gz /tmp

RUN cd /tmp && \
    tar xvzf apache-tomcat-8.5.43.tar.gz && \
    mv apache-tomcat-8.5.43 /opt

EXPOSE 8080

ADD http://mirrors.jenkins.io/war-stable/latest/jenkins.war /opt/apache-tomcat-8.5.43/webapps/

CMD ["/opt/apache-tomcat-8.5.43/bin/catalina.sh","run"]

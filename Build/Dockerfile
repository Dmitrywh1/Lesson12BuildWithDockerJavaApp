FROM ubuntu:18.04 as build
RUN apt-get update
RUN apt install maven -y
RUN apt install openjdk-11-jdk -y
RUN apt install git -y
RUN git clone https://github.com/shephertz/App42PaaS-Java-MySQL-Sample.git
RUN cd App42PaaS-Java-MySQL-Sample/ && mvn package

FROM tomcat:9.0.8-jre8-alpine
COPY --from=build App42PaaS-Java-MySQL-Sample/target/App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT.war /usr/local/tomcat/webapps

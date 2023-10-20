FROM ubuntu:18.04 as build
RUN apt-get update
RUN apt install openjdk-11-jdk git maven -y
RUN git clone https://github.com/Dmitrywh1/Lesson12Repo.git
RUN cd Lesson12Repo/ && mvn package

FROM tomcat:9.0.8-jre8-alpine
COPY --from=build Lesson12Repo/target/App42PaaS-Java-MySQL-Sample-0.0.1-SNAPSHOT.war /usr/local/tomcat/webapps
COPY --from=build Lesson12Repo/WebContent/Config.properties /usr/local/tomcat/ROOT/
